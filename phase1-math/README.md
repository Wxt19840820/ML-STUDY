# 📐 Phase 1 · 数学基础

**时间：第 1–6 周（共 42 天）**
**每日投入：1.5–2 小时**
**目标：建立 ML 所需的数学直觉，不追求完美，够用即可**

---

## 模块总览

| 模块 | 内容 | 周次 |
|------|------|------|
| 1.1 线性代数 | 向量、矩阵、特征值、SVD | Week 1–2 |
| 1.2 微积分 & 优化 | 导数、梯度、梯度下降 | Week 3–4 |
| 1.3 概率论 & 统计 | 概率、分布、MLE、贝叶斯 | Week 5–6 |

---

## 📺 可访问的学习资源

### 线性代数
| 资源 | 链接 |
|------|------|
| 线代的本质 (3Blue1Brown) | https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab |
| MIT 18.06 Linear Algebra | https://www.youtube.com/playlist?list=PL49CF3715CB9EF31D |
| Mathematics for ML (免费PDF) | https://mml-book.github.io/book/mml-book.pdf |
| Khan Academy 线代 | https://www.khanacademy.org/math/linear-algebra |

### 微积分 & 优化
| 资源 | 链接 |
|------|------|
| 微积分的本质 (3Blue1Brown) | https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr |
| Khan Academy 微积分 | https://www.khanacademy.org/math/calculus-1 |
| CS229 数学补充笔记 | https://cs229.stanford.edu/section/cs229-linalg.pdf |

### 概率论 & 统计
| 资源 | 链接 |
|------|------|
| StatQuest | https://www.youtube.com/@statquest |
| 贝叶斯定理 (3Blue1Brown) | https://www.youtube.com/watch?v=HZGCoVF3YvM |
| Think Stats (免费在线书) | https://greenteapress.com/thinkstats2/html/index.html |

---

## 📅 每日计划

### Week 1 · 线性代数基础
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 1 | 向量：定义/加法/数乘/点积/范数 | 3B1B 第1-2集 | 1.5h |
| Day 2 | 矩阵与线性变换 | 3B1B 第3-4集 | 1.5h |
| Day 3 | 矩阵乘法 + NumPy 练习 | 3B1B 第5集 | 2h |
| Day 4 | 行列式的几何含义 | 3B1B 第6-7集 | 1.5h |
| Day 5 | 逆矩阵/列空间/零空间 | 3B1B 第7集 | 1.5h |
| Day 6 | NumPy 线代实操 | 自己写代码验证 | 2h |
| Day 7 | 复习 & 整理笔记 | — | 1h |

### Week 2 · 线性代数进阶
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 8 | 点积与投影 | 3B1B 第9集 | 1.5h |
| Day 9 | 特征值与特征向量 | 3B1B 第14集 | 2h |
| Day 10 | PCA 直觉 | StatQuest PCA: https://www.youtube.com/watch?v=FgakZw6K1QQ | 1.5h |
| Day 11 | SVD 分解原理 | MIT 18.06 Lec 29 | 2h |
| Day 12 | NumPy 实现 PCA（不用sklearn）| 写代码 | 2h |
| Day 13 | 线代解释线性回归 | 推导正规方程 | 2h |
| Day 14 | 自测 & 复习 | 见文末自测题 | 1h |

### Week 3 · 微积分上篇
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 15 | 导数定义 & 基本公式 | 3B1B 微积分 第1-3集 | 1.5h |
| Day 16 | 链式法则（神经网络核心）| 3B1B 微积分 第4集 | 2h |
| Day 17 | 偏导数 & 梯度 | Khan Academy | 2h |
| Day 18 | 梯度下降直觉 + 代码实现 | 手写代码 | 2h |
| Day 19 | 学习率大小影响可视化实验 | Python + matplotlib | 2h |
| Day 20 | 泰勒展开 & 二阶优化 | 教材自学 | 1.5h |
| Day 21 | 复习 | — | 1h |

### Week 4 · 优化理论
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 22 | 凸函数 & 凸优化 | CS229: https://cs229.stanford.edu/notes2022fall/cs229-notes1.pdf | 2h |
| Day 23 | SGD vs Mini-batch GD 对比 | 写对比代码 | 2h |
| Day 24 | Adam/Momentum 原理 | 论文摘要 | 1.5h |
| Day 25 | PyTorch autograd 入门 | https://pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html | 2h |
| Day 26 | 实现简单计算图 | 写代码 | 2h |
| Day 27 | 手推逻辑回归梯度 + 验证 | 推导 + 代码 | 2h |
| Day 28 | 复习 | — | 1h |

### Week 5 · 概率论
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 29 | 概率基础/条件概率 | Khan Academy | 1.5h |
| Day 30 | 贝叶斯定理 | 3B1B 贝叶斯视频 | 1.5h |
| Day 31 | 常见分布（正态/伯努利/泊松）| StatQuest 系列 | 2h |
| Day 32 | 中心极限定理 | StatQuest: https://www.youtube.com/watch?v=YAlJCEDH2uY | 1.5h |
| Day 33 | 期望、方差、协方差 | 推导 + NumPy 实验 | 2h |
| Day 34 | 最大似然估计 (MLE) | CS229 Notes | 2h |
| Day 35 | 复习 | — | 1h |

### Week 6 · 统计 & 信息论
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 36 | MAP 估计 vs MLE | CS229 Notes | 1.5h |
| Day 37 | 假设检验基础 | StatQuest | 1.5h |
| Day 38 | 信息熵 | 3B1B: https://www.youtube.com/watch?v=v68zYyaEmEA | 1.5h |
| Day 39 | 交叉熵 & 为何用作损失函数 | 推导 + 代码 | 2h |
| Day 40 | KL 散度 | 教材 | 1.5h |
| Day 41 | CS229 习题练习 | https://cs229.stanford.edu/problem-sets/ | 2h |
| Day 42 | **Phase 1 总复习 🎉** | 整理笔记 | 2h |

---

## ✅ 阶段毕业自测

- [ ] NumPy 实现 PCA（不调 sklearn），鸢尾花数据集降到 2D 并绘图
- [ ] 手推 MSE 损失对权重 w 的梯度，代码验证
- [ ] 从 MLE 推导出交叉熵损失函数
- [ ] 解释正则化（Ridge）从 MAP 角度的含义
- [ ] 做完 CS229 Problem Set 1 第 1 题
