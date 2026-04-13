---
标题: Token 使用统计
创建时间: 2026-04-12 11:51:53
类别: 统计
标签: [token, 成本, 统计]
---

# Token 使用统计

## 今日数据 (2026-04-12)

| 模型 | 输入 Token | 输出 Token | 总 Token | 成本 (USD) |
|------|-----------|-----------|---------|-----------|
| - | - | - | - | - |

> 数据由 Hermes Agent 每日自动记录。当前无历史数据，从今日开始追踪。

今日总计: 待更新

## 近 7 天趋势

```dataview
TABLE sum(输入) as "总输入", sum(输出) as "总输出", sum(成本) as "总成本"
FROM "Token记录"
WHERE date >= date(today) - dur(7 days)
GROUP BY date
SORT date DESC
```

## 月度汇总

```dataview
TABLE sum(成本) as "总成本", avg(每日Token) as "日均 Token"
FROM "Token记录"
WHERE date >= date(today) - dur(30 days)
```

## 数据记录机制

- 记录频率: 每日 23:59 自动记录
- 记录方式: Hermes Agent 调用 cron job
- 存储位置: Token记录/YYYY-MM-DD.md
- 字段: 模型, 输入, 输出, 总成本, 备注

## 手动更新

如需手动添加当日记录，在 Token记录/ 目录下创建文件即可，Dataview 会自动聚合。

---

最后更新: 2026-04-12 11:51:53
下一更新: 今日 23:59 (自动)
