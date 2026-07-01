# Phase 6 补充 · 大模型推理服务化

> 追加到 `phase6-mlops/README.md` 的 Week 46–47 模型服务章节

---

## Week 47 补充（Day 328–336）· LLM 推理框架

### 为什么专门学 LLM 服务化？

普通 ML 模型（sklearn、小 PyTorch 模型）用 FastAPI + ONNX 就够了。
但 LLM 推理有独特挑战：

| 挑战 | 普通模型 | LLM |
|------|---------|-----|
| 显存 | 几百 MB | 几 GB 到几百 GB |
| 推理模式 | 一次前向 | 自回归，逐 token 生成 |
| 并发 | 简单 batching | Continuous Batching（连续批处理）|
| 延迟 | 毫秒级 | 首 token 延迟 + 生成速度 |
| 内存 | 固定 | KV Cache 动态增长 |

---

### Day 328 · vLLM：生产部署首选

**vLLM 核心创新：PagedAttention**

传统 KV Cache：为每个请求预分配固定大小的连续内存块，即使序列很短也占用大块内存（内部碎片），并发请求多时大量显存浪费。

PagedAttention：把 KV Cache 切成固定大小的 Page（类似 OS 的内存分页），按需分配，不同请求可以共享 Physical Page（前缀共享），几乎消除碎片。

**效果**：
- 吞吐量相比 HuggingFace 原生推理提升 **20-24 倍**
- 支持更高并发
- 支持前缀缓存（同一 System Prompt 的 KV Cache 复用）

**安装和快速上手**：
```bash
pip install vllm

# 启动 OpenAI 兼容的 API 服务（兼容 OpenAI SDK）
python -m vllm.entrypoints.openai.api_server \
    --model Qwen/Qwen2-7B-Instruct \
    --tensor-parallel-size 1 \
    --gpu-memory-utilization 0.9 \
    --max-model-len 8192 \
    --port 8000
```

**调用方式（和 OpenAI API 完全一样）**：
```python
from openai import OpenAI

client = OpenAI(base_url="http://localhost:8000/v1", api_key="token")
response = client.chat.completions.create(
    model="Qwen/Qwen2-7B-Instruct",
    messages=[{"role": "user", "content": "你好"}],
    max_tokens=512,
    temperature=0.7
)
print(response.choices[0].message.content)
```

**资源**：
- 官方文档：https://docs.vllm.ai
- GitHub：https://github.com/vllm-project/vllm
- PagedAttention 论文：https://arxiv.org/abs/2309.06180

---

### Day 329 · TGI（Text Generation Inference）

**HuggingFace 出品的推理框架**，生产级，支持所有 HF Hub 上的模型。

**特点**：
- 原生支持 HuggingFace Hub 模型（直接用模型 ID）
- 内置 Flash Attention、Continuous Batching
- 支持量化（AWQ、GPTQ、BitsAndBytes）
- 内置 Prometheus 监控指标
- Docker 一行部署

**Docker 部署**：
```bash
# 需要 NVIDIA GPU + Docker
docker run --gpus all \
    -p 8080:80 \
    -v ~/.cache/huggingface:/data \
    ghcr.io/huggingface/text-generation-inference:2.0 \
    --model-id Qwen/Qwen2-7B-Instruct \
    --max-input-length 4096 \
    --max-total-tokens 8192
```

**调用**：
```python
from huggingface_hub import InferenceClient
client = InferenceClient(model="http://localhost:8080")
response = client.text_generation("你好", max_new_tokens=100, stream=True)
for token in response:
    print(token, end="", flush=True)
```

**资源**：
- 官方文档：https://huggingface.co/docs/text-generation-inference
- GitHub：https://github.com/huggingface/text-generation-inference

---

### Day 330 · Ollama：本地部署最简方案

**最适合学习和本地测试**，无需 GPU（CPU 也能跑小模型）：

```bash
# macOS/Linux 安装
curl -fsSL https://ollama.ai/install.sh | sh

# 下载并运行模型（自动下载，国内速度可能慢）
ollama run qwen2:7b

# Python 调用
import ollama
response = ollama.chat(
    model='qwen2:7b',
    messages=[{'role': 'user', 'content': '解释什么是机器学习'}]
)
print(response['message']['content'])
```

**资源**：https://ollama.ai

---

### Day 331 · 推理性能指标

面试必考，要能清晰定义：

| 指标 | 定义 | 典型值 |
|------|------|-------|
| TTFT（首 Token 时延）| 发请求到收到第一个 token | <500ms（好）|
| TPS（Token/秒）| 每秒生成的 token 数 | 50-200 TPS/请求 |
| 吞吐量 | 整个系统每秒 token 总数 | 越高越好 |
| GPU 利用率 | 显存和计算单元的利用程度 | >80%（目标）|

**优化手段总结**：

```
减小模型体积：量化（INT8/INT4）、蒸馏、剪枝
提升吞吐量：Continuous Batching、PagedAttention
减少计算：Flash Attention、KV Cache、投机采样
多卡并行：Tensor Parallel、Pipeline Parallel
```

---

### Day 332 · Continuous Batching（连续批处理）

**传统 Static Batching 问题**：
一批请求里最短的生成了 10 个 token，最长的要生成 200 个。
最短的那个完成后，GPU 空转等待其他请求，浪费算力。

**Continuous Batching**：
每生成完一个请求，立刻把等待队列里的新请求插入 batch，GPU 永远满负荷。

```
时刻 t=0：[请求A, 请求B, 请求C] 进入
时刻 t=5：请求A 生成完毕 → [请求D, 请求B, 请求C] 继续
时刻 t=8：请求B 生成完毕 → [请求D, 请求E, 请求C] 继续
```

**效果**：GPU 利用率从 ~40% 提升到 ~90%+，吞吐量提升 3-5 倍。
vLLM 和 TGI 都默认开启。

---

### Day 333 · 投机采样（Speculative Decoding）

**问题**：LLM 自回归生成，每步只生成一个 token，GPU 利用率低（矩阵乘法对 batch_size=1 效率很低）。

**投机采样思路**：
1. 用小模型（Draft Model，如 68M）快速猜 4-5 个 token
2. 用大模型（Target Model，如 7B）一次并行验证所有猜测
3. 猜对的直接接受，猜错的从错误位置重新采样

**效果**：速度提升 2-3 倍，质量等同于大模型独立生成。
代价：需要额外维护一个小模型。

---

### Day 334–336 · 实战：搭建完整 LLM API 服务

**项目目标**：本地搭建一个 OpenAI 兼容的 LLM 服务，带监控和日志

**技术栈**：
```
Ollama（本地模型，无需 GPU）
或 vLLM（有 GPU 时）
↓
FastAPI（包一层自定义逻辑：认证、限流、日志）
↓
Prometheus + Grafana（监控 TPS、TTFT、错误率）
↓
Docker Compose（一键启动）
```

**项目结构**：
```
llm-api-service/
├── docker-compose.yml
├── app/
│   ├── main.py          # FastAPI 路由
│   ├── middleware.py    # 限流、认证、日志
│   └── metrics.py       # Prometheus 指标
├── prometheus.yml
└── README.md
```

**docker-compose.yml 示例**：
```yaml
version: '3'
services:
  ollama:
    image: ollama/ollama
    volumes:
      - ~/.ollama:/root/.ollama
    ports:
      - "11434:11434"

  api:
    build: ./app
    ports:
      - "8000:8000"
    environment:
      - LLM_BASE_URL=http://ollama:11434
    depends_on:
      - ollama

  prometheus:
    image: prom/prometheus
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml
    ports:
      - "9090:9090"
```

**资源**：
- vLLM 官方文档：https://docs.vllm.ai/en/latest/
- TGI 文档：https://huggingface.co/docs/text-generation-inference
- Ollama：https://ollama.ai
- 投机采样论文：https://arxiv.org/abs/2302.01318

---

## ✅ 本补充模块自测

- [ ] 解释 PagedAttention 为什么能减少显存碎片
- [ ] 说出 vLLM 和 TGI 的 3 个核心区别
- [ ] 用 Ollama 在本地跑起来一个 LLM，并用 Python 调用
- [ ] 解释 Continuous Batching 和 Static Batching 的区别
- [ ] 给一个 LLM 服务，说出应该监控哪 4 个核心指标及正常范围
