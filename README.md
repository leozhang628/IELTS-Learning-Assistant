# IELTS Learning Assistant System

Enhanced RAG System with Dynamic Relevance Assessment for IELTS preparation.

## 项目概述

IELTS Learning Assistant System是一个智能学习助手，基于增强检索增强生成(RAG)技术，专为IELTS考生设计。系统通过动态相关性评估机制，提供高度相关的学习资源和个性化反馈，帮助用户高效备考。

## 系统架构

系统分为三个主要部分：

### 1. 预处理阶段（离线）

- **文本数据收集**：整合IELTS教材和学习资源
- **句子分割**：使用spaCy将文本分割为10句话的语义块
- **嵌入生成**：使用all-mpnet-base-v2模型生成768维向量表示
- **向量存储**：以CSV格式保存向量数据

### 2. 主处理流程

- **用户查询**：接收用户问题
- **向量检索**：基于点积相似度检索相关内容
- **相关内容提取**：获取Top-5相关语义块
- **相关性评估**：使用0.65阈值评估内容相关性
- **LLM生成**：使用Gemma-2b-it模型生成回答
- **结果展示**：呈现答案及相关上下文

### 3. 附加功能

- **写作评估**：评价和改进IELTS作文
- **学习计划**：生成个性化学习路线图
- **模拟测试**：提供IELTS模拟试题
- **文本转语音**：使用MMS-TTS-Eng转换文本为语音
- **进度跟踪**：记录学习进度和提供反馈

## 技术亮点

1. **动态相关性评估**：根据0.65阈值动态调整回答策略
2. **精细化语料分块**：10句话为单位的分块策略平衡上下文和精度
3. **轻量级模型选择**：使用Gemma-2b-it保证速度和质量平衡
4. **多模态交互**：结合文本和语音功能支持多种学习方式
5. **学习闭环设计**：通过进度跟踪反馈优化学习计划

## 安装说明

### 环境要求

- Python 3.8+
- PyTorch 1.12+
- Transformers 4.26+
- spaCy 3.5+

### 安装步骤

1. 克隆仓库：
\\\ash
git clone https://github.com/您的用户名/ielts-learning-assistant.git
cd ielts-learning-assistant
\\\

2. 安装依赖：
\\\ash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
\\\

3. 下载必要模型：
\\\ash
python download_models.py
\\\

## 使用方法

### 预处理数据

\\\ash
python preprocessing/run_preprocessing.py --input_dir data/sample_texts --output_dir data/embeddings
\\\

### 启动系统

\\\ash
python main.py
\\\

访问 http://localhost:5000 使用Web界面。

### API使用示例

\\\python
from core.api import IELTSAssistant

assistant = IELTSAssistant()
response = assistant.ask("如何提高IELTS写作分数?")
print(response)
\\\

## 项目结构

\\\
ielts-learning-assistant/
├── preprocessing/       # 预处理阶段代码
├── core/                # 主流程代码
├── features/            # 附加功能代码
├── ui/                  # 用户界面代码
├── data/                # 示例数据
├── models/              # 模型配置
├── requirements.txt     # 项目依赖
└── main.py              # 主程序入口
\\\

## 许可证

MIT

## 致谢

感谢SentenceTransformer、Google Gemma和Facebook MMS-TTS-Eng提供的技术支持。
