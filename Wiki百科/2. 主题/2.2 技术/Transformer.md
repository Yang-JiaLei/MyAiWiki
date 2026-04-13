---
title: Transformer
created: 2026-04-12
updated: 2026-04-12
type: topic
category: ai
tags: [transformer, architecture, attention, deep-learning]
---

# 🔄 Transformer 架构

> **"Attention Is All You Need"** — Vaswani et al., 2017

## 📖 核心思想

抛弃传统的 CNN/RNN，完全基于**自注意力机制（Self-Attention）** 构建序列模型。

### 关键组件

1. **自注意力**：计算序列内所有位置的关联度
2. **前馈网络**：每位置独立变换
3. **层归一化**：稳定训练
4. **位置编码**：注入顺序信息

## 🌟 影响

Transformer 是当今几乎所有 LLM 的基础架构：
- GPT 系列（Decoder-only）
- BERT 系列（Encoder-only）
- T5、BART（Encoder-Decoder）

## 🔗 关联

- [[Wiki百科/1. 实体/1.3 产品/gpt.md]] — 基于 Transformer
- [[Wiki百科/2. 主题/2.2 技术/LLM.md|LLM]] — 使用 Transformer
- [[Wiki百科/1. 实体/1.1 人物/andrej-karpathy.md|Andrej Karpathy]] — 教学视频解析 Transformer

## 📚 参考

- [原始论文](https://arxiv.org/abs/1706.03762)
- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)

---

> "Attention is all you need." — 论文标题
