---
title: Gemini
created: 2026-04-15
updated: 2026-04-23
type: topic
category: ai-models
related:
  - [[Wiki百科/1. 实体/1.4 工具/gemini-cli.md]]
  - [[Wiki百科/1. 实体/1.2 公司/Google.md]]
  - [[Wiki百科/1. 实体/1.2 公司/openai.md]]
  - [[Wiki百科/1. 实体/1.3 产品/gpt.md]]
---

# Gemini

Google DeepMind 开发的大语言模型系列，支持文本、图像、音频、视频等多模态输入，在 Google AI Studio 和 Gemini CLI 中可用。

## 模型系列

### Gemini 2.5 系列（最新）
- **Gemini 2.5 Pro** — 旗舰模型，支持百万级上下文
- **Gemini 2.5 Flash** — 轻量高速版本

### Gemini 2.0 系列
- **Gemini 2.0 Flash** — 平衡性能与速度
- **Gemini 2.0 Pro** — 进阶推理能力

### Gemini 1.5 系列
- **Gemini 1.5 Pro** — 百万上下文支持
- **Gemini 1.5 Flash** — 快速响应

## 访问方式

| 方式 | 适用场景 | 说明 |
|------|---------|------|
| **Gemini Web** | 普通用户 | https://gemini.google.com |
| **Google AI Studio** | 开发者快速原型 | https://aistudio.google.com，获取 API Key |
| **Vertex AI** | 企业级生产部署 | Google Cloud 全托管服务 |
| **gemini-cli** | 命令行交互、脚本集成 | 本地终端使用，支持文件上传 |

## 核心能力

- **长上下文:** Gemini 1.5+ 支持百万 token 上下文
- **多模态输入:** 图像、PDF、音频、视频理解
- **代码生成:** 支持 Python、JavaScript、Go 等语言
- **工具调用:** 函数调用、网页搜索（需配置）
- **思考模式:** 2.5 系列支持展示推理过程

## 与 CLI 的集成

通过 `gemini-cli` 工具，可以在终端直接使用 Gemini：

```bash
# 安装
npm install -g @google/gemini-cli

# 使用 API Key 认证
export GEMINI_API_KEY=你的密钥

# 交互模式
gemini

# 单次查询
gemini "你的问题"
```

详细配置见 [[Wiki百科/1. 实体/1.4 工具/gemini-cli.md]]。

## 相关主题

- [[Wiki百科/2. 主题/2.3 方法论/Prompt Engineering.md]] — 优化与 Gemini 的交互提示
- [[Wiki百科/1. 实体/1.3 产品/Google AI Studio.md|Google AI Studio]] — 获取 API Key 和测试
- [[Wiki百科/2. 主题/2.2 技术/LLM.md]] — 大语言模型概述
## 定义

Gemini 是 Google 体系中的模型系列专题页。

## 核心观点

- 该页适合承载模型族谱与能力演进
- 工具接入和开发者入口应分别落到实体页

## 关键方法或机制

- 多模态输入
- 长上下文支持
- 模型系列分层

## 相关实体

- [[Wiki百科/1. 实体/1.2 公司/Google.md|Google]]
- [[Wiki百科/1. 实体/1.3 产品/Google AI Studio.md|Google AI Studio]]
- [[Wiki百科/1. 实体/1.4 工具/gemini-cli.md|gemini-cli]]

## 相关来源

- [[Wiki百科/3. 原始来源/3.1 文章/gemini-cli-README.md|Gemini CLI README]]

## 开放问题

- 需要继续补齐 Gemini 各版本与能力边界的时间标签
