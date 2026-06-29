# 🚀 Phase 6 · 工程化 & MLOps

**时间：第 45–52 周（共 56 天）**
**目标：将模型从实验室带到生产，掌握现代 ML 工程栈**

---

## 模块总览
| 模块 | 内容 | 周次 |
|------|------|------|
| 6.1 数据工程 | 数据管道、特征存储、版本控制 | Week 45 |
| 6.2 模型服务 | FastAPI、ONNX、量化、推理优化 | Week 46–47 |
| 6.3 容器化 & 云 | Docker、CI/CD、云平台部署 | Week 48–49 |
| 6.4 实验管理 | MLflow、W&B、DVC | Week 50 |
| 6.5 监控 & 迭代 | 数据漂移、A/B 测试 | Week 51 |
| 6.6 毕业大项目 | 端到端完整 ML 系统 | Week 52 |

---

## 📺 学习资源

| 资源 | 链接 |
|------|------|
| Full Stack Deep Learning | https://fullstackdeeplearning.com/course/2022/ |
| Made With ML | https://madewithml.com |
| MLOps Zoomcamp | https://github.com/DataTalksClub/mlops-zoomcamp |
| FastAPI 文档 | https://fastapi.tiangolo.com |
| Docker 入门 | https://docs.docker.com/get-started/ |
| MLflow 文档 | https://mlflow.org/docs/latest/index.html |
| DVC 文档 | https://dvc.org/doc |
| Weights & Biases | https://docs.wandb.ai |
| Evidently AI | https://docs.evidentlyai.com |
| GitHub Actions | https://docs.github.com/actions |
| HuggingFace Spaces（免费部署）| https://huggingface.co/docs/hub/spaces |
| Railway（免费部署）| https://docs.railway.app |
| Render（免费部署）| https://render.com |
| Chip Huyen 博客 | https://huyenchip.com/blog/ |

---

## 📅 每日计划

### Week 45 · 数据工程
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 309 | DVC 数据版本控制 | https://dvc.org/doc/start | 2h |
| Day 310 | Great Expectations 数据验证 | https://docs.greatexpectations.io/docs/tutorials/quickstart/ | 2h |
| Day 311 | sklearn Pipeline 封装全流程 | sklearn 文档 | 1.5h |
| Day 312 | Feast 特征存储概念 | https://docs.feast.dev/getting-started/quickstart | 1.5h |
| Day 313 | 实现简单数据管道 | 自己实现 | 2h |
| Day 314–315 | 整理 & 复习 | — | — |

### Week 46–47 · 模型服务
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 316 | FastAPI 基础（路由/Pydantic/响应）| FastAPI 教程 Ch1-3 | 2h |
| Day 317 | 包装 ML 模型为 REST API | 自己实现 | 2h |
| Day 318 | 异步推理 async/await | FastAPI 异步文档 | 1.5h |
| Day 319 | 模型序列化（pickle/joblib/ONNX）| ONNX: https://onnx.ai | 1.5h |
| Day 320 | ONNX 导出 & onnxruntime 推理 | PyTorch ONNX 文档 | 2h |
| Day 321 | pytest + httpx 写 API 测试 | 自己实现 | 1.5h |
| Day 323 | 模型量化（INT8）| https://pytorch.org/docs/stable/quantization.html | 2h |
| Day 325 | 知识蒸馏 | https://arxiv.org/abs/1503.02531 | 2h |
| Day 327 | locust 压力测试 | https://locust.io | 1.5h |

### Week 48–49 · Docker & 云部署
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 330 | Docker 基础 | Docker 官方入门 | 2h |
| Day 331 | ML 应用 Dockerfile | 自己实现 | 2h |
| Day 332 | Docker Compose 多服务 | Docker Compose 文档 | 2h |
| Day 337 | GitHub Actions CI/CD | GitHub Actions 文档 | 2h |
| Day 338 | 自动化测试流水线 | 自己实现 | 2h |
| Day 340 | Railway/Render 免费部署 | https://docs.railway.app | 2h |
| Day 341 | HuggingFace Spaces 部署 | HF Spaces 文档 | 1.5h |

### Week 50 · 实验管理
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 344 | MLflow 追踪实验 | https://mlflow.org/docs/latest/quickstart.html | 2h |
| Day 345 | MLflow Model Registry | MLflow 文档 | 1.5h |
| Day 346 | W&B 实战 & sweep | https://docs.wandb.ai/quickstart | 2h |
| Day 347 | DVC Pipeline 可重现实验 | DVC 文档 | 2h |

### Week 51 · 监控 & 迭代
| 天 | 任务 | 资源 | 时间 |
|----|------|------|------|
| Day 351 | Evidently 数据漂移检测 | https://docs.evidentlyai.com/get-started/tutorial | 2h |
| Day 352 | 模型性能监控方案设计 | 自己设计 | 2h |
| Day 353 | A/B 测试框架 | 自己实现 | 2h |
| Day 355 | Sentry 错误监控 | https://sentry.io/for/python/ | 1.5h |

### Week 52 · 毕业大项目

**选项 A：智能问答 API 服务**
技术：FastAPI + LangChain + Chroma + Docker + GitHub Actions → Railway

**选项 B：图像识别微服务**
技术：FastAPI + ONNX Runtime + Docker + Redis + Render 部署

**必须包含：**
- README.md（项目介绍 + 架构图 + 运行方式）
- Dockerfile（一键容器化）
- docker-compose.yml（一键启动）
- .github/workflows/（自动 CI/CD）
- tests/（API 测试用例）

| 天 | 任务 |
|----|------|
| Day 358 | 需求设计 & 架构图 |
| Day 359–362 | 开发实现 |
| Day 363 | 部署 & 测试 |
| Day 364 | 写完整文档 |
| Day 365 | **🎓 12 个月学习计划完成！** |

---

## ✅ Phase 6 毕业自测
- [ ] 有公开访问的 ML 服务 URL
- [ ] 有 Dockerfile 一键容器化
- [ ] 有 GitHub Actions 自动化 CI/CD
- [ ] 有 MLflow/W&B 实验追踪记录
- [ ] 有数据漂移监控机制
- [ ] GitHub 个人主页有完整 ML 作品集 README
