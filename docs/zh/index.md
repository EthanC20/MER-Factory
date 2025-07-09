---
layout: default
title: MER-Factory - 多模态情感识别工厂
description: 用于构建多模态情感识别和推理(MERR)数据集的自动化工厂
lang: zh
---

<div class="hero-section">
  <h1 class="hero-title">👉🏻 MER-Factory 👈🏻</h1>
  <p class="hero-subtitle">您用于构建多模态情绪识别与推理 (MERR) 数据集的自动化工厂</p>
  
  <div class="badges">
    <img src="https://img.shields.io/badge/Task-Multimodal_Emotion_Reasoning-red" alt="MERR">
    <img src="https://img.shields.io/badge/Task-Multimodal_Emotion_Recognition-red" alt="MER">
    <img src="https://img.shields.io/badge/Python-3.12+-blue" alt="Python">
    <img src="https://img.shields.io/badge/License-MIT-green" alt="License">
  </div>

  <img src="../assets/logo.png" alt="MER-Factory 标志" class="hero-image">
</div>

## 快速概览

MER-Factory 是一个**基于 Python 的开源框架**，专为情感计算社区设计。它通过提取多模态特征并利用大型语言模型 (LLM) 生成详细分析和情感推理摘要，从而自动化创建用于训练多模态大型语言模型 (MLLM) 的统一数据集。

### 🚀 核心功能

- **多管道架构**: 支持 AU、音频、视频、图像和完整的 MER 处理
- **灵活的模型集成**: 支持 OpenAI、Google Gemini、Ollama 和 Hugging Face 模型
- **可扩展处理**: 对大型数据集进行异步/并发处理
- **科学基础**: 基于面部动作编码系统 (FACS) 和最新研究
- **易用的 CLI 界面**: 简单的命令行用法和全面的选项

### 📋 处理类型

| 管道 | 描述 | 用例 |
|----------|-------------|----------|
| **AU** | 面部动作单元提取与描述 | 面部表情分析 |
| **Audio** | 语音转录与音调分析 | 音频情绪分析 |
| **Video** | 全面的视频内容描述 | 视频情绪分析 |
| **Image** | 静态图像情绪识别 | 基于图像的情绪分析 |
| **MER** | 完整的多模态管道 | 完整的情感推理数据集 |

## 快速开始

```bash
# 安装 MER-Factory
git clone https://github.com/Lum1104/MER-Factory.git
cd MER-Factory
pip install -r requirements.txt

# 配置环境
cp .env.example .env
# 编辑 .env 文件，填入您的 API 密钥和 OpenFace 路径

# 运行完整的 MER 管道
python main.py video.mp4 output/ --type MER --silent
```

### 📖 输出示例

查看 MER-Factory 生成的真实示例：
- [Gemini 模型输出](https://github.com/Lum1104/MER-Factory/blob/main/examples/gemini_merr.json)
- [LLaVA 模型输出](https://github.com/Lum1104/MER-Factory/blob/main/examples/llava-llama3:latest_llama3.2_merr_data.json)

## 架构概览

<div class="architecture-section">
  <h3>系统组件</h3>
  <ul>
    <li><strong>CLI 框架:</strong> 使用 Typer 构建强大的命令行界面</li>
    <li><strong>工作流管理:</strong> 使用 LangGraph 实现有状态处理管道</li>
    <li><strong>面部分析:</strong> 使用 OpenFace 提取面部动作单元</li>
    <li><strong>媒体处理:</strong> 使用 FFmpeg 进行音频/视频操作</li>
    <li><strong>AI 集成:</strong> 支持多个 LLM 提供商的可插拔架构</li>
    <li><strong>并发处理:</strong> 使用 Asyncio 实现高效的并行处理</li>
  </ul>
</div>

## 入门指南

准备好深入了解了吗？以下是您需要知道的内容：

1.  **[先决条件](/MER-Factory/zh/getting-started#prerequisites)** - 安装 FFmpeg 和 OpenFace
2.  **[安装指南](/MER-Factory/zh/getting-started#installation)** - 设置 MER-Factory
3.  **[基本用法](/MER-Factory/zh/getting-started#your-first-pipeline)** - 您的第一个情绪识别管道
4.  **[模型配置](/MER-Factory/zh/getting-started#model-options)** - 选择并配置您的 AI 模型
5.  **[高级功能](/MER-Factory/zh/getting-started#next-steps)** - 探索所有功能

## 社区与支持

- 📚 **[技术文档](/MER-Factory/zh/technical-docs)** - 深入了解系统架构
- 🔧 **[API 参考](/MER-Factory/zh/api-reference)** - 完整的函数和类文档
- 💡 **[示例](/MER-Factory/zh/examples)** - 真实世界的使用示例和教程
- 🐛 **问题与错误报告** - [GitHub Issues](https://github.com/Lum1104/MER-Factory/issues)
- 💬 **讨论** - [GitHub Discussions](https://github.com/Lum1104/MER-Factory/discussions)

*与情感计算社区共同进步。*

<style>
.hero-section {
  text-align: center;
  margin: 2rem 0;
  padding: 2rem;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  border-radius: 10px;
}

.hero-title {
  font-size: 2.5rem;
  margin-bottom: 0.2rem;
  color: #2c3e50;
}

.hero-subtitle {
  font-size: 1.2rem;
  color: #7f8c8d;
  margin-bottom: 0.2rem;
}

.badges {
  margin: 0.3rem 0;
  display: inline-block;
  text-align: center;
}

.badges img {
  height: 28px;
  margin: 0.4rem;
  vertical-align: middle;
  border: none;
  background: none;
  box-shadow: none;
}

.hero-image {
  max-width: 30%;
  width: auto;
  height: auto;
  margin: 0.5rem auto;
  display: block;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

/* 响应式设计 */
@media (max-width: 768px) {
  .hero-image {
    width: 90%;
  }
  
  .badges {
    display: block;
    text-align: center;
  }
}

.architecture-section {
  background: #f8f9fa;
  padding: 1.5rem;
  border-radius: 8px;
  margin: 1.5rem 0;
}


table {
  width: 100%;
  border-collapse: collapse;
  margin: 1rem 0;
}

table th, table td {
  padding: 0.75rem;
  text-align: left;
  border-bottom: 1px solid #dee2e6;
}

table th {
  background-color: #f8f9fa;
  font-weight: 600;
}
</style>