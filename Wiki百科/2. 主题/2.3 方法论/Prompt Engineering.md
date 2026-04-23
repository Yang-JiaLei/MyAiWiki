---
title: Prompt Engineering
created: 2026-04-12
updated: 2026-04-23
type: topic
category: ai
tags: [prompt, engineering, llm, ai]
---

# 🎯 Prompt Engineering（提示工程）

> 设计和优化与 AI 模型交互的文本提示，以获得最佳输出

## 📖 定义

Prompt Engineering 是一门关于如何构造有效提示（prompt）来引导大语言模型生成期望结果的学科。

## 🔑 核心技术

### 1. 角色扮演（Role Prompting）
让模型扮演特定角色以提升输出质量。
```text
你是一位经验丰富的软件工程师...
```

### 2. 少样本学习（Few-Shot Learning）
提供示例展示期望的输入输出格式。

### 3. 思维链（Chain-of-Thought）
引导模型逐步推理。
```text
让我们一步一步思考...
```

### 4. 自洽性（Self-Consistency）
多次采样取最优结果。

### 5. ReAct 模式
结合推理（Reasoning）和行动（Acting）。

## 🛠️ 常用技巧

| 技巧 | 说明 | 示例 |
|------|------|------|
| **明确指令** | 清晰具体，避免模糊 | "用 3 句话总结" vs "总结" |
| **提供上下文** | 给出必要背景信息 | "你是一位医生，病人..." |
| **结构化输出** | 指定格式（JSON、表格等） | "以 JSON 格式返回..." |
| **分隔符** | 使用 """ 或 --- 分隔不同部分 | |
| **步骤分解** | 要求逐步思考 | "首先...其次...最后" |

## 📚 资源

### Prompt 库
- [[prompts.chat]] — 全球最大开源 prompt 库（4198+ prompts）
- OpenAI 官方 Prompt Engineering Guide
- Anthropic 提示设计文档

### 工具
- **OpenAI Playground** — 交互式调试
- **PromptPerfect** — 自动优化
- **DSPy** — 编程式 prompt 优化

## 🔗 关联

- [[Wiki百科/2. 主题/2.2 技术/LLM.md]] — 应用对象
- [[prompts.chat]] — prompt 集合
- [[Wiki百科/1. 实体/1.3 产品/chatgpt.md]] — 主要使用场景

## 📝 笔记

- 2026-04-12：创建主题页，集成 prompts.chat

---

> "好的 prompt 是艺术与科学的结合。" — OpenAI 研究团队
## 定义

Prompt Engineering 是围绕提示词设计、约束和迭代优化的方法论。

## 核心观点

- 高质量提示词是稳定输出的重要杠杆
- 提示词也是知识库工作流中的可复用资产

## 关键方法或机制

- 角色设定
- 示例驱动
- 分步推理
- 输出约束

## 相关实体

- [[Wiki百科/1. 实体/1.3 产品/chatgpt.md|ChatGPT]]
- [[Wiki百科/1. 实体/1.4 工具/gemini-cli.md|gemini-cli]]
- [[Wiki百科/1. 实体/1.5 项目/prompts.chat.md|prompts.chat]]

## 相关来源

- [[Wiki百科/3. 原始来源/3.1 文章/prompts-chat-PROMPTS.md|Awesome ChatGPT Prompts]]

## 开放问题

- 需要继续区分个人提示词资产和通用方法论页面
