# 人工智能通识基础

人工智能通识基础课程项目，包含深度学习实践：**BERT 中文情感分析**。

## 项目结构

```
├── train_bert.ipynb           # BERT 微调：微博评论 6 分类情感识别
├── bert_pred.ipynb            # BERT 推理：对 QQ 群聊天记录进行情感预测
├── data_cleaning.ipynb        # 数据清洗：预处理聊天记录 Excel 文件
├── visualization.ipynb        # 可视化：绘制情感随时间变化趋势图
├── data/                      # 数据集（FashionMNIST、微博情感、聊天记录）
├── trained_model/             # 训练好的 BERT 模型权重 (~409 MB/epoch)
└── bert-base-chinese/         # HuggingFace 预训练中文 BERT 模型
```

## 工作流

### 1. BERT 中文情感分析 (`train_bert.ipynb` → `bert_pred.ipynb` → `visualization.ipynb`)

基于 `bert-base-chinese` 微调 6 分类情感模型（快乐、愤怒、悲伤、恐惧、惊讶、中性）：

- **训练数据**：微博 SMP2020 EWECT 数据集（~27,768 条标注数据）
- **最佳准确率**：76.6%（Epoch 4）
- **应用**：对上海大学学盟 QQ 群聊天记录进行情感预测与趋势可视化

### 完整情感分析流程：

```
data_cleaning.ipynb           # 清洗原始聊天记录
       ↓
bert_pred.ipynb               # BERT 模型推理，预测每条消息的情感
       ↓
visualization.ipynb           # 绘制 2025.09 – 2026.03 情感趋势图
```

## 环境依赖

- Python 3.x
- PyTorch / torchvision
- HuggingFace Transformers
- Pandas
- Matplotlib
- tqdm

## 运行方式

使用 VS Code 或 Jupyter 按顺序运行各 `.ipynb` 文件。训练前需将 `bert-base-chinese/` 预训练模型放入项目根目录。
