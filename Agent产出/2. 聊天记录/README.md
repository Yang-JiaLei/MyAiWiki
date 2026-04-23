---
title: 聊天记录
created: 2026-04-15
updated: 2026-04-15
type: index
category: agent-chat
---

# 聊天记录

放与 AI 的对话历史和回溯材料。

```dataview
TABLE file.link as 页面
FROM "Agent产出/2. 聊天记录"
WHERE file.name != "README"
SORT file.name
```
