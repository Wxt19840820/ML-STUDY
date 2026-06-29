# 📚 推荐资源汇总（全部免费/有免费版本）

---

## 🎥 视频课程

### 数学基础
| 课程 | 链接 |
|------|------|
| 线代的本质 (3Blue1Brown) | https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab |
| 微积分的本质 (3Blue1Brown) | https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr |
| MIT 18.06 线性代数 | https://www.youtube.com/playlist?list=PL49CF3715CB9EF31D |
| StatQuest | https://www.youtube.com/@statquest |

### 机器学习
| 课程 | 链接 |
|------|------|
| Andrew Ng ML Specialization | https://www.coursera.org/specializations/machine-learning-introduction |
| Andrew Ng Deep Learning | https://www.coursera.org/specializations/deep-learning |
| Kaggle Learn | https://www.kaggle.com/learn |

### 深度学习
| 课程 | 链接 |
|------|------|
| fast.ai | https://course.fast.ai |
| Karpathy NN Zero to Hero | https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ |
| MIT 6.S191 | https://introtodeeplearning.com |
| CS231n | https://cs231n.github.io |
| CS224n | https://web.stanford.edu/class/cs224n/ |
| HuggingFace NLP Course | https://huggingface.co/learn/nlp-course |
| HuggingFace RL Course | https://huggingface.co/learn/deep-rl-course |

### MLOps
| 课程 | 链接 |
|------|------|
| Full Stack Deep Learning | https://fullstackdeeplearning.com/course/2022/ |
| Made With ML | https://madewithml.com |
| MLOps Zoomcamp | https://github.com/DataTalksClub/mlops-zoomcamp |

---

## 📖 书籍（全部免费）

| 书名 | 链接 | 阶段 |
|------|------|------|
| Mathematics for ML | https://mml-book.github.io/book/mml-book.pdf | Phase 1 |
| Think Stats | https://greenteapress.com/thinkstats2/html/index.html | Phase 1 |
| ISL (统计学习导论) | https://www.statlearning.com/ | Phase 3 |
| ESL (统计学习基础) | https://hastie.su.domains/ElemStatLearn/ | Phase 3 进阶 |
| 动手学深度学习（中文）| https://zh.d2l.ai | Phase 4 |
| Deep Learning Book | https://www.deeplearningbook.org | Phase 4 |
| Neural Networks and DL | http://neuralnetworksanddeeplearning.com | Phase 4 |

---

## 🛠️ 环境安装

```bash
# 创建环境
conda create -n ml python=3.11
conda activate ml

# 科学计算栈
pip install numpy pandas matplotlib seaborn scipy

# 机器学习
pip install scikit-learn xgboost lightgbm optuna shap

# 深度学习（CPU）
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu

# 深度学习（CUDA 11.8）
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

# NLP
pip install transformers datasets tokenizers accelerate peft

# Demo & 可视化
pip install plotly gradio streamlit

# MLOps
pip install mlflow wandb dvc evidently fastapi uvicorn
```

---

## 🆓 免费 GPU

| 平台 | 链接 | GPU |
|------|------|-----|
| Google Colab | https://colab.research.google.com | T4/V100 |
| Kaggle Notebooks | https://www.kaggle.com/code | P100/T4（每周30h）|
| HuggingFace Spaces | https://huggingface.co/spaces | 小 GPU 免费 |

---

## 🆓 免费部署

| 平台 | 链接 | 适合 |
|------|------|------|
| HuggingFace Spaces | https://huggingface.co/spaces | Gradio/Streamlit Demo |
| Railway | https://railway.app | FastAPI 服务 |
| Render | https://render.com | Web 服务 |

---

## 📝 必读博客

| 文章 | 链接 |
|------|------|
| Karpathy 博客 | https://karpathy.github.io |
| 神经网络训练 Recipe | https://karpathy.github.io/2019/04/25/recipe/ |
| Illustrated Transformer | https://jalammar.github.io/illustrated-transformer/ |
| Colah LSTM | https://colah.github.io/posts/2015-08-Understanding-LSTMs/ |
| Chip Huyen 博客 | https://huyenchip.com/blog/ |
| 提示工程指南中文 | https://www.promptingguide.ai/zh |
| distill.pub | https://distill.pub |

---

## 🏆 实战平台

| 平台 | 链接 |
|------|------|
| Kaggle | https://www.kaggle.com |
| HuggingFace Hub | https://huggingface.co |
| Papers With Code | https://paperswithcode.com |
| arXiv | https://arxiv.org |

---

## 🗂️ 数据集

| 数据集 | 链接 |
|--------|------|
| UCI ML Repository | https://archive.ics.uci.edu/ml/datasets.php |
| Kaggle Datasets | https://www.kaggle.com/datasets |
| HuggingFace Datasets | https://huggingface.co/datasets |
| Roboflow Universe | https://universe.roboflow.com |
| Google Dataset Search | https://datasetsearch.research.google.com |

---

## 💬 中文社区

| 社区 | 链接 |
|------|------|
| DataWhale（开源学习）| https://github.com/datawhalechina |
| 动手学深度学习论坛 | https://discuss.d2l.ai/c/chinese-version/16 |
| 机器之心 | https://www.jiqizhixin.com |
| PaperWeekly | https://www.paperweekly.site |
