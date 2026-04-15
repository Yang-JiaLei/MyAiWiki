---
title: 页面Schema
created: 2026-04-15
updated: 2026-04-15
type: schema
category: wiki-ops
tags: [schema, template, metadata]
---

# 页面Schema

## 通用 Frontmatter

```yaml
---
title:
created:
updated:
type:
category:
tags: []
aliases: []
source_status:
confidence:
---
```

## 实体页

- `type: entity`
- 必备区块：
  - 是什么
  - 关键事实
  - 相关主题
  - 相关来源
  - 待验证点

## 主题页

- `type: topic`
- 必备区块：
  - 定义
  - 核心观点
  - 关键方法或机制
  - 相关实体
  - 相关来源
  - 开放问题

## 来源页

- `type: source`
- 必备区块：
  - 来源信息
  - 核心摘要
  - 关键主张
  - 影响到的页面
  - 原文链接
  - 处理状态

## 研究问题页

- `type: research-question`
- 必备区块：
  - 问题
  - 为什么重要
  - 已知信息
  - 缺口
  - 后续行动

## type 枚举

- `index`
- `entity`
- `topic`
- `source`
- `research-question`
- `rule`
- `workflow`
- `schema`
- `checklist`
- `ledger`
- `report`
- `template`
- `standard`
- `schedule`

## 字段约定

- `source_status`:
  - `raw`
  - `processed`
  - `integrated`
  - `needs-review`
- `confidence`:
  - `low`
  - `medium`
  - `high`
