---
title: 打卡系统
created: 2026-04-19
updated: 2026-04-19
type: index
category: personal-checkin
tags: [checkin, dashboard, habit]
---

# 打卡系统

这套系统只做一件事：让你每天留下一个最小但有用的管理记录。

## 快速入口

- [[个人存货/6. 打卡系统/每日打卡/2026-04-19|今日打卡]]
- [[个人存货/6. 打卡系统/打卡说明|打卡说明]]
- [[个人存货/6. 打卡系统/打卡模板|打卡模板]]

## 最近打卡

```dataview
TABLE date as 日期, mood as 心情, energy as 精力, focus as 今日重点, completed as 已完成
FROM "个人存货/6. 打卡系统/每日打卡"
WHERE date
SORT date DESC
LIMIT 14
```

## 使用原则

- 每天只建一页
- 先写今日重点，再写结果
- 不追求长，追求连续
- 一页至少回答：今天做什么、状态怎样、有没有完成
