---
title: 个人存货
created: 2026-04-12 11:51:53
updated: 2026-04-15
type: index
category: personal
tags: [personal, projects, notes, prompts]
---

# 个人存货

这是你自己的原生内容区。

这里放你亲手写的项目资料、学习记录、工作笔记、思考碎片和个人 Prompt 资产，不放外部知识的正式沉淀，不放 Agent 的中间过程产物。

## 使用规则

- 先看 [[个人存货/准入规则|准入规则]]
- 自己写的内容优先放这里
- 外部资料先去 `Wiki百科/3. 原始来源`
- AI 过程稿、抓取结果、研究中间件先去 `Agent产出`
- 已经稳定、可复用的外部知识再进入 `Wiki百科`

## 分类导航

### 1. 项目

- [[个人存货/1. 项目/README|项目入口]]
- 放你自己的项目说明、配置、运行记录、决策文档

### 2. 学习笔记

- [[个人存货/2. 学习笔记/README|学习笔记入口]]
- 放学习过程、工作日报、教程实操记录、环境配置总结

### 3. 技能树

- [[个人存货/3. 技能树/README|技能树入口]]
- 放能力地图、订阅清单、技能成长计划和能力盘点

### 4. 思考碎片

- [[个人存货/4. 思考碎片/README|思考碎片入口]]
- 放未定稿想法、问题草图、观察和短笔记

### 5. Prompt库

- [[个人存货/5. Prompt库/README|Prompt库入口]]
- 放你长期复用的个人提示词资产

## 最近更新

```dataview
TABLE file.link as 页面, file.mtime as 修改时间
FROM "个人存货"
WHERE file.name != "README" AND file.name != "准入规则"
SORT file.mtime DESC
LIMIT 15
```
