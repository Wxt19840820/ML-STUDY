# 🌲 Phase 3 · 经典机器学习

**时间：第 11–20 周（共 70 天）**
**目标：理解主流算法原理，能用 scikit-learn 解决真实问题，完成 Kaggle 竞赛**

---

## 模块总览
| 模块 | 内容 | 周次 |
|------|------|------|
| 3.1 线性模型 | 线性回归、逻辑回归、正则化 | Week 11–12 |
| 3.2 树模型 | 决策树、随机森林、XGBoost | Week 13–14 |
| 3.3 其他算法 | SVM、KNN、朴素贝叶斯 | Week 15 |
| 3.4 无监督学习 | K-Means、DBSCAN、PCA、t-SNE | Week 16–17 |
| 3.5 模型评估 & 调优 | 交叉验证、特征工程、Pipeline | Week 18–19 |
| 3.6 综合项目 | Kaggle 竞赛端到端 | Week 20 |

---

## 📺 学习资源

| 资源 | 链接 |
|------|------|
| Andrew Ng ML Specialization | https://www.coursera.org/specializations/machine-learning-introduction |
| Kaggle Learn | https://www.kaggle.com/learn |
| StatQuest ML 系列 | https://www.youtube.com/@statquest |
| CS229 Stanford 课件 | https://cs229.stanford.edu/lectures-spring2022/main_notes.pdf |
| sklearn 官方文档 | https://scikit-learn.org/stable/user_guide.html |
| XGBoost 文档 | https://xgboost.readthedocs.io/en/stable/ |
| LightGBM 文档 | https://lightgbm.readthedocs.io/en/stable/ |
| SHAP 文档 | https://shap.readthedocs.io/en/latest/ |
| Kaggle Titanic | https://www.kaggle.com/c/titanic |
| Kaggle House Prices | https://www.kaggle.com/c/house-prices-advanced-regression-techniques |
| ISL 书（免费 PDF）| https://www.statlearning.com/ |

---

## 📅 关键每日计划

### Week 11–12 · 线性模型
| 天 | 任务 | 资源 |
|----|------|------|
| Day 71 | 线性回归：最小二乘推导 | CS229 Notes Ch1 |
| Day 72 | NumPy 手实现线性回归（梯度下降+正规方程）| 写代码 |
| Day 73 | Ridge(L2) & Lasso(L1) 正则化 | StatQuest Ridge: https://www.youtube.com/watch?v=Q81RR3yKn30 |
| Day 74 | sklearn 线性回归：加州房价实战 | sklearn 文档 |
| Day 75 | 逻辑回归：Sigmoid & 决策边界 | Andrew Ng Week 3 |
| Day 76 | NumPy 手实现逻辑回归 | 写代码 |
| Day 77 | 复习 | — |
| Day 78 | 多分类：OvR/Softmax | sklearn 文档 |
| Day 79 | 混淆矩阵/精确率/召回率/F1 | StatQuest: https://www.youtube.com/watch?v=Kdsp6soqA7o |
| Day 80 | ROC & AUC | StatQuest: https://www.youtube.com/watch?v=4jRBRDbJemM |
| Day 81 | 类别不平衡处理 | imbalanced-learn: https://imbalanced-learn.org/stable/ |
| Day 82 | 垃圾邮件分类项目 | 自己实现 |
| Day 83 | 代码整理 & GitHub | — |
| Day 84 | 复习 | — |

### Week 13–14 · 树模型
| 天 | 任务 | 资源 |
|----|------|------|
| Day 85 | 决策树：信息增益 & 基尼系数 | StatQuest: https://www.youtube.com/watch?v=7VeUPuFGJHk |
| Day 86 | 手实现简单决策树（50行代码）| 写代码 |
| Day 87 | 过拟合可视化 & 剪枝 | sklearn 示例 |
| Day 88 | Bagging 原理 | StatQuest: https://www.youtube.com/watch?v=sVriC_Ys2cw |
| Day 89 | 随机森林：特征随机 & OOB | StatQuest: https://www.youtube.com/watch?v=J4Wdy0Wc_xQ |
| Day 90 | sklearn 随机森林实战 + 特征重要性 | Titanic 数据集 |
| Day 91 | 复习 | — |
| Day 92 | Boosting 原理 & AdaBoost | StatQuest: https://www.youtube.com/watch?v=LsK-xG1cLYA |
| Day 93 | Gradient Boosting | StatQuest: https://www.youtube.com/watch?v=3CC4N4z3GJc |
| Day 94 | XGBoost 核心创新 | XGBoost 文档 |
| Day 95 | Kaggle Titanic 实战（目标前20%）| https://www.kaggle.com/c/titanic |
| Day 96 | Optuna 超参数调优 | https://optuna.org |
| Day 97 | LightGBM vs XGBoost 对比 | 自己实验 |
| Day 98 | 复习 | — |

### Week 15 · 其他算法
| 天 | 任务 | 资源 |
|----|------|------|
| Day 99 | SVM 最大间隔 | StatQuest: https://www.youtube.com/watch?v=efR1C6CvhmE |
| Day 100 | 核函数：RBF & 多项式 | StatQuest: https://www.youtube.com/watch?v=Toet3EiSFcM |
| Day 101 | sklearn SVM 实战 | sklearn 文档 |
| Day 102 | KNN 算法 | StatQuest: https://www.youtube.com/watch?v=HVXime0nQeI |
| Day 103 | 朴素贝叶斯：文本分类 | sklearn 文档 |
| Day 104 | 5 算法大比拼（同一数据集）| 自己实现 |
| Day 105 | 整理 | — |

### Week 16–17 · 无监督学习
| 天 | 任务 | 资源 |
|----|------|------|
| Day 106 | K-Means 原理 | StatQuest: https://www.youtube.com/watch?v=4b5d3muPQmA |
| Day 107 | K-Means++ & Elbow 法 | sklearn 文档 |
| Day 108 | DBSCAN 密度聚类 | sklearn 聚类指南 |
| Day 109 | 层次聚类 & 树状图 | sklearn 文档 |
| Day 110 | 聚类评估（轮廓系数）| sklearn metrics |
| Day 111 | PCA 推导 | MML Book Ch10 |
| Day 112 | PCA 实战（人脸 Eigenfaces）| sklearn PCA 示例 |
| Day 113 | t-SNE | https://distill.pub/2016/misread-tsne/ |
| Day 114 | UMAP | https://umap-learn.readthedocs.io |
| Day 115 | 异常检测：IsolationForest | sklearn 文档 |
| Day 116 | 关联规则 Apriori | http://rasbt.github.io/mlxtend/ |
| Day 117 | 聚类综合项目 | 自选数据集 |
| Day 118–119 | 整理 & 复习 | — |

### Week 18–19 · 模型评估 & 特征工程
| 天 | 任务 | 资源 |
|----|------|------|
| Day 120 | K 折交叉验证 | sklearn CV 文档 |
| Day 121 | 偏差-方差权衡 | Andrew Ng 讲解 |
| Day 122 | 学习曲线 & 验证曲线 | sklearn learning_curve |
| Day 123 | 特征选择：Filter/Wrapper/Embedded | sklearn 文档 |
| Day 124 | 特征编码：One-Hot/Target Encoding | category_encoders |
| Day 125 | 特征缩放 | sklearn preprocessing |
| Day 126 | 缺失值处理策略 | sklearn SimpleImputer |
| Day 127 | Pipeline（防数据泄露）| sklearn Pipeline 文档 |
| Day 128 | 模型堆叠 Stacking | sklearn StackingClassifier |
| Day 129 | SHAP 可解释性 | https://shap.readthedocs.io |
| Day 130 | Kaggle House Prices 实战 | https://www.kaggle.com/c/house-prices-advanced-regression-techniques |
| Day 131–133 | 继续 Kaggle + 整理 | — |

### Week 20 · 综合项目
| 天 | 任务 |
|----|------|
| Day 134 | 选题 & 数据收集 |
| Day 135 | 深度 EDA |
| Day 136 | 特征工程 |
| Day 137 | 建模 & Optuna 调参 |
| Day 138 | SHAP 可解释性分析 |
| Day 139 | 写完整报告 & 博客 |
| Day 140 | **Phase 3 完成 🎉** |

---

## ✅ 阶段毕业自测
- [ ] 手推线性回归梯度更新公式，代码验证
- [ ] Kaggle Titanic 进入前 30%（score > 0.78）
- [ ] 用 Pipeline 封装预处理 + 建模全流程
- [ ] 用 SHAP 分析并解释某一预测结果的特征贡献
