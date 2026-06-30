<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&duration=3000&pause=1000&color=6366F1&center=true&vCenter=true&width=600&lines=🤖+机器学习自学计划;ML+Study+Roadmap+2026;从零基础到工程落地" alt="Typing SVG" />

<br/>

[![Phase](https://img.shields.io/badge/当前阶段-Phase_1_数学基础-6366f1?style=for-the-badge&logo=bookstack&logoColor=white)](./phase1-math/README.md)
[![Days](https://img.shields.io/badge/计划天数-365天-06b6d4?style=for-the-badge&logo=googlecalendar&logoColor=white)](#)
[![Daily](https://img.shields.io/badge/每日投入-1.5~2小时-f59e0b?style=for-the-badge&logo=clockify&logoColor=white)](#)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)](./LICENSE)
[![Stars](https://img.shields.io/github/stars/Wxt19840820/ML-STUDY?style=for-the-badge&color=f59e0b)](https://github.com/Wxt19840820/ML-STUDY/stargazers)

<br/>

> 📌 **一份从数学基础到工程落地的 ML 自学计划** | 12个月 · 365天每日任务 · 全中文 · 资源100%免费

<br/>

**[📖 开始学习](#-学习路线图) · [📚 资源汇总](./resources.md) · [🏗️ 实战项目](./projects/README.md) · [📓 每日记录](#-每日记录格式)**

</div>

---

## 📊 学习进度总览

| 阶段 | 内容 | 周次 | 进度 | 状态 |
|:----:|:-----|:----:|:----:|:----:|
| 🔢 **Phase 1** | [数学基础](./phase1-math/README.md) | 第 1–6 周 | `░░░░░░░░░░` 0% | ⬜ 进行中 |
| 🐍 **Phase 2** | [Python 编程](./phase2-python/README.md) | 第 7–10 周 | `░░░░░░░░░░` 0% | 🔒 未开始 |
| 🌲 **Phase 3** | [经典机器学习](./phase3-classical-ml/README.md) | 第 11–20 周 | `░░░░░░░░░░` 0% | 🔒 未开始 |
| 🧠 **Phase 4** | [深度学习](./phase4-deep-learning/README.md) | 第 21–36 周 | `░░░░░░░░░░` 0% | 🔒 未开始 |
| 🎯 **Phase 5** | [方向专精 NLP/CV/RL](./phase5-specialization/README.md) | 第 37–44 周 | `░░░░░░░░░░` 0% | 🔒 未开始 |
| 🚀 **Phase 6** | [工程化 & MLOps](./phase6-mlops/README.md) | 第 45–52 周 | `░░░░░░░░░░` 0% | 🔒 未开始 |

> 💡 **使用说明**：每完成一个阶段，把进度条 `░` 改为 `█`，状态改为 `✅ 已完成`

---

## 🗺️ 学习路线图

```
🔢 Phase 1 · 数学基础（第1-6周）
├── 线性代数 ──── 向量 · 矩阵 · 特征值 · SVD
├── 微积分优化 ── 导数 · 梯度 · 梯度下降
└── 概率统计 ──── 分布 · 最大似然 · 贝叶斯 · 信息熵
        ↓
🐍 Phase 2 · Python 编程（第7-10周）
├── Python核心 ── OOP · 装饰器 · 生成器
├── 科学计算 ──── NumPy · Pandas
└── 可视化 ─────  Matplotlib · Seaborn · EDA
        ↓
🌲 Phase 3 · 经典机器学习（第11-20周）
├── 监督学习 ──── 线性回归 · 逻辑回归 · SVM · 决策树
├── 集成方法 ──── 随机森林 · XGBoost · LightGBM
├── 无监督学习 ── K-Means · PCA · t-SNE
└── 模型评估 ──── 交叉验证 · 特征工程 · Pipeline · SHAP
        ↓
🧠 Phase 4 · 深度学习（第21-36周）
├── 神经网络 ──── MLP · 反向传播 · PyTorch
├── CNN ────────  LeNet · ResNet · 迁移学习
├── 序列模型 ──── RNN · LSTM · Seq2Seq
├── Transformer ─ 注意力机制 · BERT · GPT · LoRA
└── 生成模型 ──── GAN · VAE · 扩散模型
        ↓
🎯 Phase 5 · 方向专精（第37-44周）
├── NLP ─────── 文本 · RAG · 大模型微调
├── CV ──────── 目标检测 · 分割 · 多模态
└── RL ──────── Q-Learning · PPO · 游戏AI
        ↓
🚀 Phase 6 · 工程化 & MLOps（第45-52周）
├── 模型服务 ── FastAPI · ONNX · 量化
├── 容器化 ──── Docker · CI/CD · 云部署
├── 实验管理 ── MLflow · W&B · DVC
└── 监控迭代 ── 数据漂移 · A/B测试
```

---

## ⚡ 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/Wxt19840820/ML-STUDY.git
cd ML-STUDY
```

### 2. 创建 Python 环境

```bash
# 推荐使用 conda
conda create -n ml python=3.11 -y
conda activate ml

# 安装依赖
pip install -r requirements.txt

# 验证安装
python -c "import torch; import sklearn; print('✅ 环境配置成功！')"
```

### 3. 开始第一天学习

```bash
# 查看 Phase 1 详细计划
cat phase1-math/README.md

# 每天学完后记录
echo "记录今天的学习内容到 phase1-math/daily-log.md"
```

---

## 📁 仓库结构

```
ML-STUDY/
├── 📄 README.md                    ← 总览 & 进度追踪
├── 📄 requirements.txt             ← Python 依赖（一键安装）
├── 📄 .gitignore                   ← 忽略无用文件
├── 📄 LICENSE                      ← MIT 开源协议
├── 📄 resources.md                 ← 书单 · 课程 · 工具大全
│
├── 📁 phase1-math/
│   ├── 📄 README.md                ← 详细每日计划（含资源链接）
│   ├── 📓 daily-log.md             ← 每日学习记录
│   └── 📁 code/                    ← 练习代码（每天提交！）
│       ├── week1_linear_algebra.py
│       └── week2_pca_svd.py
│
├── 📁 phase2-python/               ← 同上结构
├── 📁 phase3-classical-ml/         ← 同上结构
├── 📁 phase4-deep-learning/        ← 同上结构
├── 📁 phase5-specialization/       ← 同上结构
├── 📁 phase6-mlops/                ← 同上结构
│
└── 📁 projects/
    └── 📄 README.md                ← 4个里程碑项目指南
```

---

## 🏆 四大里程碑项目

<table>
<tr>
<td align="center" width="25%">

### 🎯 项目一
**Titanic 生存预测**

`scikit-learn`
`XGBoost`
`SHAP`

📅 Phase 3 末

</td>
<td align="center" width="25%">

### 🖼️ 项目二
**图像分类 Web App**

`PyTorch`
`ResNet`
`Gradio`

📅 Phase 4 末

</td>
<td align="center" width="25%">

### 🤖 项目三
**知识库问答系统**

`LangChain`
`RAG`
`Streamlit`

📅 Phase 5 末

</td>
<td align="center" width="25%">

### 🚀 项目四
**端到端 ML 系统**

`FastAPI`
`Docker`
`CI/CD`

📅 Phase 6 末

</td>
</tr>
</table>

---

## 📚 核心资源（全部免费）

### 🎥 必看视频课程

| 资源 | 阶段 | 链接 |
|------|:----:|------|
| 线代的本质 · 3Blue1Brown | Phase 1 | [▶️ YouTube](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) |
| 微积分的本质 · 3Blue1Brown | Phase 1 | [▶️ YouTube](https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr) |
| StatQuest 统计 & ML | Phase 1–3 | [▶️ YouTube](https://www.youtube.com/@statquest) |
| Andrew Ng ML 课程 | Phase 3 | [🎓 Coursera（免费旁听）](https://www.coursera.org/specializations/machine-learning-introduction) |
| fast.ai 深度学习 | Phase 4 | [🌐 官网](https://course.fast.ai) |
| Karpathy: NN Zero to Hero | Phase 4 | [▶️ YouTube](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) |
| HuggingFace NLP Course | Phase 5 | [🌐 官网（免费）](https://huggingface.co/learn/nlp-course) |
| Full Stack Deep Learning | Phase 6 | [🌐 官网（免费）](https://fullstackdeeplearning.com/course/2022/) |

### 📖 必读书籍（全部有免费版）

| 书名 | 阶段 | 链接 |
|------|:----:|------|
| Mathematics for Machine Learning | Phase 1 | [📥 免费PDF](https://mml-book.github.io/book/mml-book.pdf) |
| 统计学习导论 ISLR | Phase 3 | [📥 免费PDF](https://www.statlearning.com/) |
| 动手学深度学习（中文）| Phase 4 | [🌐 在线阅读](https://zh.d2l.ai) |
| Deep Learning Book | Phase 4 | [🌐 在线阅读](https://www.deeplearningbook.org) |

> 📖 完整资源清单（数据集、工具、社区）见 [resources.md](./resources.md)

---

## 📓 每日记录格式

每天学完后在对应阶段的 `daily-log.md` 填一条，然后 `git push`：

```markdown
### Day 1 · 2026-07-01

**今日任务：** 向量基础 — 定义、加法、点积
**实际用时：** 1.5h
**完成情况：** ✅ 完成

**今日学到：**
- 向量点积 a·b = |a||b|cosθ，表示一个向量在另一个方向上的投影长度
- 矩阵本质是"线性变换"，不只是数字的表格

**遇到的困难：**
- 行空间和列空间的关系还不够清晰，明天重看 3B1B 第7集

**明天计划：**
- 3Blue1Brown 第3集：矩阵与线性变换
- 完成 NumPy 矩阵运算练习
```

---

## 🌟 学完后掌握的技术栈

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/🤗_HuggingFace-FFD21E?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-FF6600?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square)

</div>

---

## 💬 常见问题

<details>
<summary><b>Q：没有数学基础可以学吗？</b></summary>
<br/>
完全可以。Phase 1 从最基础的向量讲起，推荐 3Blue1Brown 系列，全程动画讲直觉，高中数学水平就够。
</details>

<details>
<summary><b>Q：没有 GPU 怎么办？</b></summary>
<br/>
前三阶段完全不需要 GPU。Phase 4 起可用 Google Colab（免费 T4）或 Kaggle Notebooks（免费 P100，每周30小时），完全够用。
</details>

<details>
<summary><b>Q：每天只有 1 小时，可以学吗？</b></summary>
<br/>
可以，时间线延长到约 20 个月。核心原则是"每天都动手"，比一周偷懒6天、第7天学8小时效果好很多。
</details>

<details>
<summary><b>Q：Phase 5 应该选哪个方向？</b></summary>
<br/>

- **NLP**：就业面最广，大模型时代最热，推荐大多数人选这个
- **CV**：落地场景最直观（自动驾驶、安防、医疗影像）
- **RL**：门槛最高，适合对算法和游戏感兴趣的人

</details>

<details>
<summary><b>Q：学完能找到工作吗？</b></summary>
<br/>
完成 Phase 1-4 可竞争初级 ML 工程师岗位。Phase 5-6 完成后，拥有 4 个可展示的完整项目，竞争力大幅提升。
</details>

---

## 📈 TODO · 持续更新计划

- [ ] 每天往 `code/` 目录提交练习代码
- [ ] Phase 3 末：完成 Titanic Kaggle 竞赛并记录分数
- [ ] Phase 4 末：部署一个可访问的 Demo 到 HuggingFace Spaces
- [ ] 每阶段末更新进度条和状态
- [ ] 补充各阶段面试题（5道/阶段）

---

<div align="center">

**⭐ 如果这个仓库对你有帮助，欢迎 Star！你的支持是坚持下去的动力 ⭐**

<br/>

🗓️ 开始时间：**2026-07-01** &nbsp;|&nbsp; 预计完成：**2027-07-01**

<br/>

[![GitHub stars](https://img.shields.io/github/stars/Wxt19840820/ML-STUDY?style=social)](https://github.com/Wxt19840820/ML-STUDY/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/Wxt19840820/ML-STUDY?style=social)](https://github.com/Wxt19840820/ML-STUDY/forks)

</div>
