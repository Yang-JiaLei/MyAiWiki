---
title: LLM
created: 2026-04-12
updated: 2026-04-23
type: topic
category: ai
tags: [llm, ai, language-model, nlp]
---

# 🤖 大语言模型（LLM）

> **Large Language Model** — 大规模语言模型

## 📖 定义

使用大规模参数（通常数亿到数万亿）在海量文本上预训练的神经网络模型，具备语言理解、生成和推理能力。

## 🔑 核心特性

### 涌现能力
规模达到临界点后，模型突然表现出小模型没有的能力：
- 上下文学习（In-context Learning）
- 指令遵循（Instruction Following）
- 逐步推理（Chain-of-Thought）

### 缩放法则（Scaling Laws）
性能随模型规模、数据量、计算量平滑增长，具有可预测性。

## 📈 主要模型系列

| 模型 | 公司 | 特点 |
|------|------|------|
| **GPT 系列** | OpenAI | Decoder-only，API 生态 |
| **Claude** | Anthropic | 安全对齐，长上下文 |
| **Gemini** | Google | 多模态原生 |
| **LLaMA** | Meta | 开源可商用 |
| **通义千问** | 阿里巴巴 | 中文优化 |
| **文心一言** | 百度 | 中文能力 |

## 🔗 关联

- [[Wiki百科/1. 实体/1.3 产品/gpt.md]] — 最具代表性的 LLM
- [[Wiki百科/2. 主题/2.2 技术/Transformer.md|Transformer]] — 底层架构
- [[Wiki百科/2. 主题/2.1 AI/RAG.md|RAG]] — 增强方案
- [[Wiki百科/2. 主题/2.1 AI/LLM-Wiki.md|LLM Wiki]] — 知识管理

## 📚 参考

- [[个人存货/1. 项目/1.4 Agent 配置.md]]
- [[日志#最近操作]]
## 定义

LLM 指在大规模文本上训练出来、具备语言理解与生成能力的大语言模型。

## 核心观点

- LLM 是当前大多数 Agent 和生成式工作流的基础能力层
- 不同模型族在多模态、推理和工具调用方面各有侧重

## 关键方法或机制

- 预训练
- 指令对齐
- 上下文推理

## 相关实体

- [[Wiki百科/1. 实体/1.2 公司/openai.md|OpenAI]]
- [[Wiki百科/1. 实体/1.3 产品/gpt.md|GPT]]
- [[Wiki百科/1. 实体/1.4 工具/gemini-cli.md|gemini-cli]]

## 相关来源

- [[Wiki百科/3. 原始来源/3.1 文章/karpathy-llm-wiki-gist.md|Karpathy LLM Wiki Gist]]

## 开放问题

- 需要进一步补齐不同模型家族的版本化比较
