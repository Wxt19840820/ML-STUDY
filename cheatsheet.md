# 📋 ML 速查表 · Cheat Sheet

> 学完各阶段后，这张表是最快的复习材料。面试前通读一遍。

---

## 🔢 数学速查

### 常用激活函数对比
| 函数 | 公式 | 范围 | 梯度问题 | 适用场景 |
|------|------|------|---------|---------|
| Sigmoid | 1/(1+e^-x) | (0,1) | 饱和区梯度≈0 | 二分类输出层 |
| Tanh | (e^x-e^-x)/(e^x+e^-x) | (-1,1) | 饱和区梯度≈0 | RNN（比Sigmoid好） |
| ReLU | max(0,x) | [0,+∞) | 负区梯度=0（死亡） | CNN、MLP默认选择 |
| Leaky ReLU | max(0.01x,x) | (-∞,+∞) | 无死亡问题 | 替代ReLU |
| GELU | x·Φ(x) | (-∞,+∞) | 平滑 | Transformer默认 |
| Softmax | e^xi/Σe^xj | (0,1) 且和=1 | — | 多分类输出层 |

### 优化器速查
| 优化器 | 特点 | 适用 |
|--------|------|------|
| SGD | 最简单，需手调lr | CV精调阶段 |
| SGD+Momentum | 加速收敛，减少震荡 | CV训练 |
| Adam | 自适应lr，收敛快 | 大多数情况默认 |
| AdamW | Adam+权重衰减解耦 | Transformer训练 |
| Lion | 只用符号，显存小 | 大模型 |

---

## 🌲 经典ML速查

### 算法对比
| 算法 | 偏差 | 方差 | 可解释性 | 适合数据量 |
|------|------|------|---------|---------|
| 线性回归 | 高 | 低 | ⭐⭐⭐⭐⭐ | 任意 |
| 决策树 | 低 | 高 | ⭐⭐⭐⭐ | 中小 |
| 随机森林 | 低 | 低 | ⭐⭐ | 中大 |
| XGBoost | 低 | 低 | ⭐⭐ | 中大 |
| SVM | 中 | 低 | ⭐ | 小中 |
| KNN | 低 | 高 | ⭐⭐⭐ | 小 |
| 朴素贝叶斯 | 高 | 低 | ⭐⭐⭐ | 任意 |

### 评估指标速查
```
准确率  = (TP+TN) / (TP+TN+FP+FN)     # 类别平衡时用
精确率  = TP / (TP+FP)                  # 关心"预测正样本有多准"（FP代价高）
召回率  = TP / (TP+FN)                  # 关心"正样本有没有漏"（FN代价高）
F1     = 2 × P × R / (P+R)             # 两者平衡
AUC    = P(正样本分数 > 负样本分数)      # 类别不平衡时用

MAE    = mean(|y - ŷ|)                 # 对异常值不敏感
MSE    = mean((y - ŷ)²)               # 对大误差惩罚更重
RMSE   = sqrt(MSE)                     # 单位和y一致
R²     = 1 - SS_res/SS_tot            # 解释方差比例，越接近1越好
```

---

## 🧠 深度学习速查

### 常见架构对比
| 架构 | 特点 | 适用任务 |
|------|------|---------|
| MLP | 全连接，忽略空间/序列信息 | 表格数据 |
| CNN | 局部感受野，平移不变性 | 图像、音频 |
| RNN/LSTM | 处理序列，有记忆 | 短序列、时序 |
| Transformer | 全局注意力，并行训练 | NLP、Vision、通用 |
| Diffusion | 扩散去噪，生成质量高 | 图像/音频生成 |

### 正则化方法速查
```
Dropout     p=0.1~0.5    随机丢弃神经元，训练时，推理时关闭
BatchNorm   默认参数      归一化激活值，加速收敛，但不适合小batch
LayerNorm   默认参数      归一化每个样本内部，Transformer默认
WeightDecay λ=1e-4~1e-2  L2正则化权重，即AdamW的weight_decay参数
数据增强     -           随机裁剪/翻转/颜色抖动，隐式正则化
```

### PyTorch 训练循环模板
```python
model.train()
for epoch in range(num_epochs):
    for batch in dataloader:
        x, y = batch
        x, y = x.to(device), y.to(device)

        optimizer.zero_grad()        # 清空梯度
        pred = model(x)              # 前向传播
        loss = criterion(pred, y)    # 计算损失
        loss.backward()              # 反向传播
        torch.nn.utils.clip_grad_norm_(model.parameters(), 1.0)  # 梯度裁剪
        optimizer.step()             # 更新参数
        scheduler.step()             # 更新学习率

    # 验证
    model.eval()
    with torch.no_grad():
        val_loss = evaluate(model, val_loader)
    model.train()
```

---

## 🚀 NLP 速查

### HuggingFace 5行完成微调
```python
from transformers import AutoModelForSequenceClassification, TrainingArguments, Trainer

model = AutoModelForSequenceClassification.from_pretrained("hfl/chinese-bert-wwm-ext", num_labels=2)
args = TrainingArguments("output", num_train_epochs=3, per_device_train_batch_size=16, eval_strategy="epoch")
trainer = Trainer(model=model, args=args, train_dataset=train_ds, eval_dataset=val_ds, compute_metrics=compute_metrics)
trainer.train()
```

### RAG 核心流程
```
离线：文档 → 切分(chunk_size=512) → Embedding → 存入VectorDB
在线：用户问题 → Embedding → TopK检索 → 拼接Prompt → LLM生成
```

### Prompt 模板
```python
SYSTEM = "你是一个专业的机器学习助手，请用简洁清晰的中文回答问题。"
USER = f"""基于以下参考资料回答问题：

{retrieved_docs}

问题：{user_question}

请基于参考资料回答，如果资料中没有相关信息，请直接说明。"""
```

---

## 🔧 MLOps 速查

### Docker 常用命令
```bash
docker build -t myapp:latest .          # 构建镜像
docker run -p 8000:8000 myapp:latest    # 运行容器
docker push registry/myapp:latest       # 推送到镜像仓库
docker compose up -d                    # 后台启动所有服务
docker logs -f container_name           # 查看实时日志
```

### FastAPI 模型服务模板
```python
from fastapi import FastAPI
from pydantic import BaseModel
import torch

app = FastAPI()
model = torch.load("model.pt")
model.eval()

class PredictRequest(BaseModel):
    text: str

@app.post("/predict")
async def predict(req: PredictRequest):
    with torch.no_grad():
        result = model(preprocess(req.text))
    return {"prediction": result.item(), "model_version": "v1.0"}

@app.get("/health")
def health():
    return {"status": "ok"}
```

### vLLM 快速启动
```bash
# 启动 OpenAI 兼容服务
python -m vllm.entrypoints.openai.api_server \
    --model Qwen/Qwen2-7B-Instruct \
    --gpu-memory-utilization 0.9

# 测试
curl http://localhost:8000/v1/chat/completions \
    -H "Content-Type: application/json" \
    -d '{"model":"Qwen/Qwen2-7B-Instruct","messages":[{"role":"user","content":"你好"}]}'
```

### GitHub Actions CI 模板
```yaml
name: CI
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v4
        with: { python-version: '3.11' }
      - run: pip install -r requirements.txt
      - run: pytest tests/ -v
      - run: docker build -t myapp .
```

---

## ⚡ 常见问题排查

| 现象 | 原因 | 解决 |
|------|------|------|
| Loss 不下降 | 学习率太小/太大 | 用学习率查找（lr finder）|
| Loss 爆炸 | 学习率太大/梯度爆炸 | 降低lr，加梯度裁剪 |
| 训练loss低验证loss高 | 过拟合 | 加Dropout/正则化/更多数据 |
| 训练慢 | batch太小/未用GPU | 加大batch，检查`device` |
| CUDA OOM | 显存不足 | 减小batch，用梯度累积/量化 |
| 模型不收敛 | 权重初始化问题/BN未开 | 检查model.train()，用标准初始化 |
| API返回502 | 容器崩溃 | `docker logs`查看错误 |
