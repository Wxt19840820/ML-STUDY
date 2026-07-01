# Phase 4 补充 · 现代 Transformer 技术

> 追加到 `phase4-deep-learning/README.md` 的 Transformer 章节末尾

---

## Week 32 补充（Day 218–224）· 现代 Transformer 优化

### 为什么需要学这些？
2024-2026 年的面试中，以下内容已经是"默认会"的水平，不是加分项：

| 技术 | 解决的问题 | 重要程度 |
|------|---------|---------|
| Flash Attention | 标准 Attention 内存 O(n²)，超长序列爆显存 | ⭐⭐⭐⭐⭐ |
| RoPE 位置编码 | 绝对位置编码外推性差，无法处理超长文本 | ⭐⭐⭐⭐⭐ |
| GQA/MQA | KV Cache 太大，推理显存占用高 | ⭐⭐⭐⭐ |
| KV Cache | 自回归推理重复计算，速度慢 | ⭐⭐⭐⭐⭐ |
| MoE | 稠密模型参数利用率低 | ⭐⭐⭐⭐ |

---

### Day 218 · Flash Attention

**核心思想**：标准 Attention 需要实例化 n×n 的注意力矩阵（n=序列长度），内存 O(n²)，2048 token 就要几 GB。
Flash Attention 利用 GPU 的 SRAM（快速片上内存），分块计算 softmax，避免全量实例化。

**结果**：
- 内存：O(n²) → O(n)
- 速度：快 2-4 倍
- 精度：数学上等价，无精度损失

**资源（均可免费访问）**：
- 论文（必读）：https://arxiv.org/abs/2205.14135
- 直觉讲解：https://gordicaleksa.medium.com/eli5-flash-attention-5c44017022ad
- PyTorch 使用：`F.scaled_dot_product_attention(q, k, v)`（PyTorch 2.0+ 自动调用 Flash Attention）

**代码（一行就够）**：
```python
# PyTorch 2.0+ 自动使用 Flash Attention
with torch.backends.cuda.sdp_kernel(enable_flash=True):
    out = F.scaled_dot_product_attention(q, k, v, is_causal=True)
```

---

### Day 219 · RoPE 位置编码

**问题**：原始 Transformer 用绝对位置编码（学习一个 embedding），训练时序列长 2048，推理时碰到 4096 就崩。

**RoPE 思想**：旋转位置编码。把位置信息编码为旋转角度，作用在 Q 和 K 上，使 Q·K 的内积只依赖于相对位置，而不是绝对位置。

**优势**：
- 外推性好（可以超出训练长度）
- 相对位置自然建模
- 被 LLaMA、GPT-NeoX、Qwen 等几乎所有主流开源模型采用

**扩展 RoPE 上下文**（面试常考）：
- YaRN：缩放 RoPE 基频，低成本把上下文扩展到 128K
- LongRoPE：微软提出，扩展到 2M token

**资源**：
- 论文：https://arxiv.org/abs/2104.09864
- 苏剑林博客（中文，最通俗）：https://kexue.fm/archives/8265

---

### Day 220 · KV Cache & GQA

**KV Cache 是什么**：
自回归生成时，每生成一个新 token 就要对所有历史 token 重新计算 K 和 V。
KV Cache 把历史的 K、V 缓存起来，每步只计算新 token 的 Q，大幅提升推理速度。

**问题**：序列越长 + batch 越大，KV Cache 越占显存。
LLaMA-2 7B，batch=1，序列长 2K：KV Cache ≈ 1.2 GB；batch=32 就是 38 GB。

**GQA（Grouped Query Attention）解决方案**：
- MHA（多头注意力）：每个头有独立的 K、V
- MQA（多查询注意力）：所有头共享一组 K、V（极端省内存，但质量下降）
- GQA（分组查询注意力）：折中，每组共享 K、V
- LLaMA-3、Mistral、Qwen 均使用 GQA

**资源**：
- GQA 论文：https://arxiv.org/abs/2305.13245
- KV Cache 直觉讲解：https://www.youtube.com/watch?v=80bIUggRJf4

---

### Day 221 · MoE（混合专家模型）

**核心思想**：把 FFN 层替换为多个"专家"（小 FFN），每个 token 只激活其中 Top-K 个专家（通常 K=2）。

**结果**：
- 模型总参数大（Mixtral 8x7B 总参数 46B）
- 但每次前向计算只用 ~13B（2个专家激活）
- 计算量和 7B 模型相当，但质量接近 70B

**代表模型**：Mixtral 8x7B、DeepSeek MoE、GPT-4（据传）

**挑战**：负载均衡（所有 token 涌向同一个专家）、推理时需要加载所有专家参数

**资源**：
- Mixtral 论文：https://arxiv.org/abs/2401.04088
- MoE 讲解：https://huggingface.co/blog/moe

---

### Day 222–224 · 实操：用 HuggingFace 体验这些技术

```python
# Flash Attention（需要 pip install flash-attn）
from transformers import AutoModelForCausalLM
model = AutoModelForCausalLM.from_pretrained(
    "Qwen/Qwen2-7B",
    attn_implementation="flash_attention_2",  # 一行开启
    torch_dtype=torch.float16
)

# 查看 KV Cache 使用情况
from transformers import DynamicCache
past_key_values = DynamicCache()
outputs = model(input_ids, past_key_values=past_key_values, use_cache=True)
print(f"KV Cache 大小: {sum(k.nbytes + v.nbytes for k,v in past_key_values.key_value_pairs) / 1e6:.1f} MB")

# 使用 GQA 模型（LLaMA-3 自动使用）
from transformers import AutoConfig
config = AutoConfig.from_pretrained("meta-llama/Meta-Llama-3-8B")
print(f"Query heads: {config.num_attention_heads}")   # 32
print(f"KV heads: {config.num_key_value_heads}")      # 8（4:1 分组）
```

---

## ✅ 本补充模块自测

- [ ] 解释 Flash Attention 为什么内存是 O(n) 而不是 O(n²)
- [ ] RoPE 和绝对位置编码的本质区别
- [ ] 为什么 GQA 能减少 KV Cache 而不太影响质量
- [ ] 给定 LLaMA-3 8B，batch=8，序列长 8192，估算 KV Cache 大小
