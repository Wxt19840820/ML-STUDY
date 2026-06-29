# 🧠 Phase 4 · 深度学习

**时间：第 21–36 周（共 112 天）**
**目标：掌握核心深度学习架构，能用 PyTorch 独立训练和调试模型**

---

## 模块总览
| 模块 | 内容 | 周次 |
|------|------|------|
| 4.1 神经网络基础 | MLP、反向传播、激活函数 | Week 21–22 |
| 4.2 CNN | 卷积、经典架构、迁移学习 | Week 23–25 |
| 4.3 训练技巧 | BN、Dropout、优化器、调参 | Week 26–27 |
| 4.4 RNN & LSTM | 序列模型、时序数据 | Week 28–29 |
| 4.5 Transformer | 注意力机制、BERT、GPT | Week 30–32 |
| 4.6 生成模型 | GAN、VAE、扩散模型 | Week 33–34 |
| 4.7 综合项目 | 端到端 DL 系统 | Week 35–36 |

---

## 📺 学习资源（全部免费）

| 资源 | 链接 |
|------|------|
| fast.ai 实用深度学习 | https://course.fast.ai |
| Karpathy: NN Zero to Hero | https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ |
| 动手学深度学习（中文）| https://zh.d2l.ai |
| MIT 6.S191 | https://introtodeeplearning.com |
| CS231n 笔记 | https://cs231n.github.io |
| CS224n | https://web.stanford.edu/class/cs224n/ |
| PyTorch 官方 60 分钟入门 | https://pytorch.org/tutorials/beginner/deep_learning_60min_blitz.html |
| HuggingFace NLP Course | https://huggingface.co/learn/nlp-course |
| Illustrated Transformer | https://jalammar.github.io/illustrated-transformer/ |
| Illustrated BERT | https://jalammar.github.io/illustrated-bert/ |
| Colah LSTM 博客 | https://colah.github.io/posts/2015-08-Understanding-LSTMs/ |
| Karpathy nanoGPT | https://github.com/karpathy/nanoGPT |
| Karpathy micrograd | https://github.com/karpathy/micrograd |
| Karpathy 训练 Recipe | https://karpathy.github.io/2019/04/25/recipe/ |

### 必读论文（免费）
| 论文 | 链接 |
|------|------|
| ResNet | https://arxiv.org/abs/1512.03385 |
| Attention Is All You Need | https://arxiv.org/abs/1706.03762 |
| BERT | https://arxiv.org/abs/1810.04805 |
| DDPM | https://arxiv.org/abs/2006.11239 |
| LoRA | https://arxiv.org/abs/2106.09685 |

---

## 📅 关键每日计划

### Week 21–22 · 神经网络基础
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 141 | 神经元 & 激活函数（ReLU/Sigmoid/GELU）| D2L Ch4.1 | 1.5h |
| Day 142 | MLP 前向传播矩阵推导 | D2L Ch4.2 | 1.5h |
| Day 143 | **反向传播**（手动推导 + 链式法则）| 3B1B: https://www.youtube.com/watch?v=Ilg3gGewQ5U | 2.5h |
| Day 144 | PyTorch Tensor & autograd | PyTorch 60分钟入门 | 2h |
| Day 145 | PyTorch 实现 MLP | 写完整训练循环 | 2h |
| Day 146 | 损失函数选择（MSE/CE/BCE）| D2L 章节 | 1.5h |
| Day 147 | 复习 | — | 1h |
| Day 148 | 权重初始化（Xavier/He）| D2L Ch4.8 | 1.5h |
| Day 149 | 优化器对比（SGD/Adam/AdamW）| D2L Ch11 | 2h |
| Day 150 | 完整训练循环（早停/保存/加载）| 写代码 | 2h |
| Day 151 | 调试技巧 | Karpathy Recipe | 2h |
| Day 152 | MNIST 项目（目标98%+）| 自己实现 | 2h |
| Day 153 | 阅读 micrograd 源码 | https://github.com/karpathy/micrograd | 2h |
| Day 154 | 复习 | — | 1h |

### Week 23–25 · CNN
| 天 | 任务 | 资源 |
|----|------|------|
| Day 155 | 卷积：stride/padding/感受野 | D2L Ch6 |
| Day 156 | 特征图可视化 | CS231n Lec5 |
| Day 157 | 池化层 | D2L Ch6.5 |
| Day 158 | LeNet-5 实现 | D2L Ch6.6 |
| Day 159 | AlexNet | D2L Ch7.1 |
| Day 160 | VGG | D2L Ch7.2 |
| Day 162 | ResNet（残差连接）| 论文 + D2L Ch7.6 |
| Day 163 | ResNet PyTorch 实现 & CIFAR-10 训练 | 写代码 |
| Day 164 | 迁移学习 | https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html |
| Day 165 | 数据增强 | torchvision.transforms 文档 |
| Day 166 | 目标检测入门（YOLO 直觉）| https://docs.ultralytics.com |
| Day 169–174 | 图像分类 Web App 项目 | Gradio: https://www.gradio.app |

### Week 26–27 · 训练技巧
| 天 | 任务 | 资源 |
|----|------|------|
| Day 176 | Dropout | D2L Ch4.6 |
| Day 177 | Batch Normalization | https://arxiv.org/abs/1502.03167 |
| Day 178 | Layer Norm | D2L Ch8.5 |
| Day 179 | 学习率调度 | PyTorch LR Scheduler 文档 |
| Day 180 | 混合精度 AMP | https://pytorch.org/tutorials/recipes/recipes/amp_recipe.html |
| Day 184 | W&B 实验管理 | https://docs.wandb.ai |

### Week 28–29 · RNN & LSTM
| 天 | 任务 | 资源 |
|----|------|------|
| Day 190 | RNN 原理 & 梯度消失 | D2L Ch9 |
| Day 191 | LSTM 门控机制 | https://colah.github.io/posts/2015-08-Understanding-LSTMs/ |
| Day 193 | PyTorch LSTM 情感分类 | 写代码 |
| Day 195 | Bahdanau 注意力机制 | D2L Ch10.4 |

### Week 30–32 · Transformer（重点）
| 天 | 任务 | 资源 |
|----|------|------|
| Day 204 | Self-Attention (Q/K/V) | https://jalammar.github.io/illustrated-transformer/ |
| Day 205 | Multi-Head Attention | D2L Ch11.5 |
| Day 207 | 完整 Transformer 架构 | Attention Is All You Need 论文 |
| Day 208–209 | **手写 Transformer**（字符级 GPT）| https://github.com/karpathy/nanoGPT |
| Day 210 | BERT 架构 | https://jalammar.github.io/illustrated-bert/ |
| Day 212 | HuggingFace 入门 | HuggingFace NLP Course Ch2 |
| Day 213 | 微调 BERT 文本分类 | HuggingFace NLP Course Ch3 |
| Day 215 | LoRA 微调 | https://huggingface.co/docs/peft |

### Week 33–34 · 生成模型
| 天 | 任务 | 资源 |
|----|------|------|
| Day 225–226 | VAE 原理 & 实现 | D2L Ch20.3 |
| Day 227–228 | GAN & DCGAN | https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html |
| Day 230 | 扩散模型直觉 | https://www.assemblyai.com/blog/diffusion-models-for-machine-learning-introduction/ |
| Day 232 | HuggingFace Diffusers 实战 | https://huggingface.co/docs/diffusers/quicktour |

### Week 35–36 · 毕业项目（三选一）
- **选项 A**：图像分类 Web App（ResNet + Gradio + HuggingFace Spaces）
- **选项 B**：中文情感分析系统（BERT + FastAPI + Docker）
- **选项 C**：图像生成应用（Stable Diffusion + ControlNet + Gradio）

---

## ✅ 阶段毕业自测
- [ ] NumPy 实现反向传播（不用 autograd）
- [ ] 解释 BatchNorm 在训练/推理时的不同行为
- [ ] 从零实现 Transformer Self-Attention
- [ ] 微调 BERT 在自定义数据集上达到合理精度
- [ ] 有可访问的深度学习 Demo（HuggingFace Spaces 免费部署）
