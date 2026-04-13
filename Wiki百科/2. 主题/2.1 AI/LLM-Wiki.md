---
title: LLM Wiki
created: 2026-04-12
updated: 2026-04-12
type: topic
category: ai
tags: [llm, wiki, knowledge-base, rag]
---

- [ ] 阅读原文并提取更多实践案例



# 🤖 LLM Wiki

> 使用 LLM 构建和维护个人知识库的模式
> 参考：[[Wiki百科/1. 实体/1.1 人物/andrej-karpathy.md|Andrej Karpathy]] 的 [LLM Wiki Gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)

## 📖 核心思想

传统的 RAG 系统每次查询都重新从原始文档中检索和生成，**没有积累**。

LLM Wiki 模式不同：**增量构建和持久维护一个 Wiki** —— 位于你和原始源之间的结构化、互链的 Markdown 文件集合。

**关键差异**：
- ✅ 知识被**编译一次**，然后保持最新
- ✅ 交叉引用已经存在
- ✅ 矛盾已经被标记
- ✅ 综合反映你读过的一切
- ✅ Wiki 是**持久化、复利增长**的产物

## 🏗️ 三层架构

### 1. Raw Sources (`raw/`)
原始源文档（只读）
- 文章、论文、书籍、笔记
- LLM 从中读取但不修改
- **单一事实来源**

### 2. The Wiki (`/`)
LLM 生成的 Markdown 文件
- 实体页、主题页、源摘要
- LLM 完全拥有这一层
- 创建、更新、维护交叉引用

### 3. Schema (`AGENTS.md`)
配置文件 — 告诉 LLM 如何结构化 Wiki

## 🔄 操作流程

### Ingest（摄入）
```
新源 → LLM 阅读 → 提取关键信息 → 
更新实体页 → 创建源摘要 → 更新索引 → 记录日志
```

单篇文章可能影响 **10-15 个 Wiki 页面**。

### Query（查询）
```
问题 → LLM 读取 index.md → 
定位相关页面 → 综合回答 → 
有价值则归档为新页面
```

### Lint（健康检查）
定期检查：
- 🕳️ 孤立页面（无 inbound 链接）
- ⚠️ 矛盾陈述
- 📅 过期信息
- 🔗 缺失的交叉引用

## 📈 为什么有效？

维护知识库的繁琐部分不是阅读或思考——是**记账**：
- 更新交叉引用
- 保持摘要最新
- 标注新数据与旧主张的矛盾
- 维护一致性

人类放弃 Wiki 是因为维护成本增长快于价值。**LLM 不会感到无聊，不会忘记更新交叉引用，一次可以修改 15 个文件**。Wiki 保持维护，因为维护成本接近于零。

**人类的职责**：策展源材料、引导分析、提出好问题、思考意义。
**LLM 的职责**：其他所有事情。

## 🔗 相关

- [[Wiki百科/1. 实体/1.1 人物/andrej-karpathy.md|Andrej Karpathy]] - 提出者
- [[Wiki百科/2. 主题/2.1 AI/RAG.md|RAG]] - 传统检索增强生成（对比）
- [[Wiki百科/1. 实体/1.3 产品/obsidian.md|Obsidian]] - 推荐的 Wiki 阅读/编辑界面
- [[个人存货/1. 项目/1.3 FastNodeSync.md|FastNodeSync]] - 实时同步方案

## 📚 参考

- [Original Gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [[日志.md#最近操作]] - 本 Wiki 的演变历史
