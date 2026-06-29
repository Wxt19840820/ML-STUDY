# 🏗️ 实战项目列表

> 每个阶段至少完成一个项目并推送到 GitHub

---

## Phase 3 · 经典 ML 项目

### 项目 1：Titanic 生存预测（必做）
- **目标**：Kaggle LB > 0.78
- **技术**：Pandas + sklearn + XGBoost
- **数据**：https://www.kaggle.com/c/titanic/data
- **参考**：https://www.kaggle.com/code/startupsci/titanic-data-science-solutions

### 项目 2：房价预测（进阶）
- **目标**：Kaggle Top 20%
- **技术**：LightGBM + XGBoost + Stacking + SHAP
- **数据**：https://www.kaggle.com/c/house-prices-advanced-regression-techniques

---

## Phase 4 · 深度学习项目

### 项目 3：图像分类器 Web App
- **功能**：上传图片 → 分类结果
- **技术**：PyTorch ResNet + Gradio
- **部署**：https://huggingface.co/spaces（免费）

### 项目 4：BERT 中文文本分类
- **技术**：HuggingFace + chinese-bert-wwm-ext
- **数据**：https://huggingface.co/datasets/tyqiangz/multilingual-sentiments

---

## Phase 5 · 方向专项

### NLP：个人知识库问答
- **技术**：LangChain + Chroma + Qwen + Streamlit
- **参考**：https://python.langchain.com/docs/use_cases/question_answering/

### CV：实时目标检测
- **技术**：YOLOv8 + Gradio + OpenCV
- **数据**：https://universe.roboflow.com

### RL：游戏 AI
- **技术**：PyTorch + Stable-Baselines3 + Gymnasium
- **参考**：https://stable-baselines3.readthedocs.io

---

## Phase 6 · 毕业大项目（端到端 ML 系统）

### 选项 A：智能文档问答 API
```
文档上传 → 解析 → 向量化 → 问答
FastAPI + LangChain + Chroma + Docker + GitHub Actions
部署：Railway（免费）
```

### 选项 B：图像识别微服务
```
图片上传 → 分类/检测 → JSON 结果
FastAPI + ONNX + Docker + Redis
部署：Render（免费）
```

---

## 项目 README 模板

```markdown
# 项目名称

## 简介
一句话描述项目。

## 在线 Demo
[链接] 或 截图

## 技术栈
- 列表

## 快速开始
\`\`\`bash
git clone https://github.com/你的名字/项目名
cd 项目名
pip install -r requirements.txt
python app.py
\`\`\`

## 项目结构
\`\`\`
项目/
├── 文件说明
\`\`\`

## 结果
指标 / 演示效果

## 参考
- 相关论文、教程
```
