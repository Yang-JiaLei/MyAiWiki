---
title: RAG
created: 2026-04-12
updated: 2026-04-23
type: topic
category: ai
tags: [rag, retrieval, ai, llm, knowledge-base]
---

# 🔍 RAG (Retrieval-Augmented Generation)

> **对比**：传统 RAG vs [[Wiki百科/2. 主题/2.1 AI/LLM-Wiki.md|LLM Wiki]] 模式

## 📖 什么是 RAG？

**检索增强生成**（Retrieval-Augmented Generation）是一种将外部知识库与 LLM 结合的技术：

```
用户问题 → 检索相关文档片段 → 拼接为 Prompt → LLM 生成答案
```

### 典型流程

1. **索引**：将文档切块 → 向量化 → 存入向量数据库
2. **检索**：问题向量化 → 相似度搜索 → Top-K 相关片段
3. **生成**：片段 + 问题 → LLM → 回答

## ⚠️ 局限性

### 无积累
每次查询都**从头开始**：
- 不记住之前的推理
- 不更新摘要
- 不维护交叉引用
- 不标记矛盾

### 重复工作
问一个需要综合 5 个文档的问题 → LLM 每次都重新查找、拼接。

### 零复利
知识不**复利增长**。今天是 100 个文档，明天还是 100 个，只是多了一个答案。

## 🆚 LLM Wiki vs RAG

| 特性 | RAG | LLM Wiki |
|------|-----|----------|
| 知识积累 | ❌ 无 | ✅ 复利增长 |
| 维护成本 | 低（只索引） | 一次投入，持续受益 |
| 交叉引用 | ❌ 无 | ✅ 自动维护 |
| 矛盾检测 | ❌ 无 | ✅ LLM 标记 |
| 查询速度 | ⚡ 快（检索） | 快（读现成摘要） |
| 更新频率 | 重新索引 | 增量更新 |

## 🎯 适用场景

### RAG 更适合
- 静态知识库（不更新）
- 大规模文档（百万级）
- 不需要深度综合
- 只要求快速查询

### LLM Wiki 更适合
- **动态知识**（持续摄入新源）
- 个人知识管理
- 需要深度理解和综合
- 追求**知识复利**

## 🔗 相关

- [[Wiki百科/2. 主题/2.1 AI/LLM-Wiki.md|LLM Wiki]] — 替代方案
- [[Wiki百科/2. 主题/2.2 技术/向量数据库.md|Vector Database]] — RAG 基础设施
- [[Wiki百科/1. 实体/1.3 产品/obsidian.md|Obsidian]] — LLM Wiki 前端

## 📚 参考

- [Original LLM Wiki Gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [[日志#最近操作]]
## 定义

RAG 是把外部检索结果拼接进生成流程的一类工作模式。

## 核心观点

- 它擅长按问题临时取回上下文
- 但不天然沉淀长期结构化知识

## 关键方法或机制

- 文档切块
- 向量化检索
- Top-K 召回后拼接到 Prompt

## 相关实体

- [[Wiki百科/1. 实体/1.3 产品/obsidian.md|Obsidian]]

## 相关来源

- [[Wiki百科/3. 原始来源/3.1 文章/karpathy-llm-wiki-gist.md|Karpathy LLM Wiki Gist]]

## 开放问题

- 在本知识库中，RAG 与 LLM Wiki 的边界还可继续细化
