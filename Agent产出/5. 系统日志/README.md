---
title: 系统日志
updated: 2026-04-15
type: index
category: agent-logs
---

# 系统日志

放自动化任务、系统运行状态和执行日志。

```dataview
TABLE file.link as 页面
FROM "Agent产出/5. 系统日志"
WHERE file.name != "README"
SORT file.name
```
