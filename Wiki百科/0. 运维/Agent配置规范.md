---
title: Agent 配置规范
created: 2026-04-12
updated: 2026-04-15
type: standard
category: wiki-ops
tags: [agent, schema, wiki, config]
---

# Agent 配置规范

> 基于 Karpathy 的 LLM Wiki 模式，适配 FastNodeSync 同步环境

这是一份运维规范，不是个人项目记录。

## 核心原则

- **LLM 是维护者**：我（LLM）负责所有 wiki 的编写、更新、交叉引用
- **你是策展人**：你负责提供源材料、提问、引导方向
- **持久化**：所有知识以结构化 Markdown 形式持久存储
- **增量积累**：每添加一个源，wiki 变得更丰富

## 三层架构

### 1. Raw Sources (`raw/`)
源文档存储区（只读）
- 保存原始文章、论文、笔记
- 按来源分类：`raw/wechat/`, `raw/papers/`, `raw/books/`
- 不修改，只引用

### 2. The Wiki (`/`)
主知识库（Markdown 文件）
- 实体页：人物、项目、概念
- 主题页：AI、编程、产品
- 源摘要：每篇源文章的摘要
- 索引：`index.md`
- 日志：`log.md`

### 3. Schema (`AGENTS.md`)
本文件 — 告诉 LLM 如何维护 wiki

## 目录结构

```
vault/
├── AGENTS.md              # 本 schema 文件
├── index.md               # 内容索引（自动更新）
├── log.md                 # 操作日志（自动更新）
├── raw/                   # 原始源文件
│   ├── wechat/           # 公众号文章
│   ├── papers/           # 学术论文
│   ├── books/            # 书籍章节
│   └── notes/            # 个人笔记
├── Entities/              # 实体页面
│   ├── People/           # 人物
│   ├── Projects/         # 项目
│   ├── Companies/        # 公司
│   └── Products/         # 产品
├── Topics/               # 主题页面
│   ├── AI/              # 人工智能
│   ├── Programming/     # 编程
│   ├── Product/         # 产品
│   └── Science/         # 科学
├── Sources/             # 源文章摘要
│   ├── Wechat/         # 公众号文章
│   ├── ArXiv/          # 论文
│   └── Books/          # 书籍
└── Meta/               # 元数据
    ├── Templates/      # 页面模板
    └── Guides/         # 使用指南
```

## Frontmatter 约定

所有 wiki 页面使用 YAML frontmatter：

```yaml
---
title: 页面标题
created: 2026-04-12
updated: 2026-04-12
type: entity|topic|source|meta
category: people|project|ai|wechat|paper
tags: [tag1, tag2]
source: source-type/reference-id  # 如果是基于某个源
aliases: [别名1, 别名2]
related: [[链接页面1], [链接页面2]]
---

- [ ] 测试 LLM 自动维护 Wiki 流程


```

## 命名约定

- 文件名：`kebab-case.md`（小写，连字符）
- 实体页：`name.md` 或 `full-name.md`
- 主题页：`topic-name.md`
- 源摘要：`YYYY-MM-DD-source-title.md`
- 重定向页：`Alias.md` → `Actual.md`（使用 redirect 插件）

## 链接约定

- 内部链接：`[[页面名]]` 或 `[[页面名|显示文本]]`
- 外部链接：`[文本](URL)`
- 块引用：`[[页面名#^block-id]]`（需插件）

## 工作流程

### Ingest（摄入源）
1. 用户提供源（链接、文件、文本）
2. LLM 阅读并提取关键信息
3. 创建/更新相关实体页
4. 创建源摘要页（`Sources/` 下）
5. 更新 `index.md`
6. 在 `log.md` 记录

### Query（查询）
1. 用户提问
2. LLM 读取 `index.md` 定位相关页面
3. 读取相关页面，综合回答
4. 如果答案有价值，创建新页面归档

### Lint（健康检查）
定期检查：
- 孤立页面（无 inbound 链接）
- 矛盾陈述
- 过期信息
- 缺失的交叉引用

## 索引格式 (`index.md`)

```markdown
# Wiki Index

## 📚 源文档
- [2026-04-12 - 公众号文章](Sources/Wechat/2026-04-12-fg2gedg.md) - 摘要...

## 👤 实体
- [[Wiki百科/1. 实体/1.1 人物/andrej-karpathy.md|Andrej Karpathy]] - Tesla AI 主管
- [[Wiki百科/1. 实体/1.2 公司/openai.md|OpenAI]] - AI 研究公司

## 🏷️ 主题
- [[Wiki百科/2. 主题/2.2 技术/LLM.md|LLM]] - 大语言模型
- [[Wiki百科/2. 主题/2.1 AI/RAG.md|RAG]] - 检索增强生成
```

## 日志格式 (`log.md`)

```markdown
## [2026-04-12 06:30] Ingest - WeChat Article
- 源：FG2gEdgZwpMkA3ApQMksnw
- 创建：Sources/Wechat/FG2g...
- 更新：[[Wiki百科/2. 主题/AI/LLM-Wiki|AI 主题]], [[Wiki百科/2. 主题/AI/LLM-Wiki|LLM Wiki]]

## [2026-04-12 06:35] Query - 什么是 LLM Wiki？
- 读取：[[个人存货/1. 项目/1.4 Agent 配置.md|AGENTS.md]], [[Wiki百科/2. 主题/2.2 技术/LLM.md|LLM]]
```

## 模板

### 实体页模板
见 `Meta/Templates/entity.md`

### 源摘要模板
见 `Meta/Templates/source.md`

### 主题页模板
见 `Meta/Templates/topic.md`

## Obsidian 插件推荐

- **Dataview**：动态查询 frontmatter
- **Graph View**：可视化连接
- **Template**：快速插入模板
- **Spaced Repetition**：记忆卡片
- **linter**：格式化
- **redirect**：别名重定向

## 与 FastNodeSync 集成

- Wiki 根目录：`/vault/`
- 自动同步到 Obsidian
- 所有修改实时上传
- 多设备访问

## 开始使用

向 LLM 发送：
> "参考 AGENTS.md，帮我把这篇公众号文章 [[链接]] 添加到知识库"

LLM 将：
1. 读取源内容
2. 提取实体和主题
3. 创建/更新页面
4. 维护索引和日志

---

**这个 schema 会随着你的需求一起演化。**


## 📋 待办任务

```dataview
TASK
FROM ""
WHERE !completed
SORT due ASC
LIMIT 20
```

### 高优先级

> 详细任务清单见 [[待办任务]]
- [ ] 填充公众号文章详情（标题、公众号名、核心内容）
- [ ] 添加更多 AI 人物（Hinton、LeCun、Bengio 等）
- [ ] 创建 GPT 系列详细页面（GPT-4、GPT-4o）
- [ ] 添加 Anthropic、Google DeepMind 等公司
- [ ] 扩展主题：Prompt Engineering、Agent、Multimodal

### 中优先级
- [ ] 在 Obsidian 中安装并配置插件
- [ ] 测试 Dataview 查询功能
- [ ] 配置 Templater 模板文件夹
- [ ] 创建每日笔记模板
- [ ] 建立项目笔记模板（用于 GitHub 项目跟踪）

### 低优先级
- [ ] 美化首页样式
- [ ] 创建 Mermaid 图表示例
- [ ] 配置同步冲突处理策略
