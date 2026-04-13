---
名称: baoyu-skills
类型: 工具
标签: [claude-code, skills, ai-agent, content-generation]
创建时间: 2026-04-12
状态: 已安装
---

# baoyu-skills

由 JimLiu 开发的 Claude Code 技能集合，包含 22 个技能，涵盖内容生成、AI 后端和日常效率工具。

## 基本信息

- **仓库**: https://github.com/jimliu/baoyu-skills
- **作者**: JimLiu
- **许可证**: MIT-0 (通过 ClawHub 发布时)
- **版本**: 0.1.0 (monorepo)
- **包管理器**: npm workspaces + bun
- **已安装**: 是 (通过 `skills add jimliu/baoyu-skills`)

## 安装方式

### 方式 1: 通过 skills CLI (推荐)

```bash
# 先安装 skills CLI
npm install -g skills

# 安装 baoyu-skills
skills add jimliu/baoyu-skills
```

### 方式 2: 通过 Claude Code 插件市场

```bash
/plugin marketplace add JimLiu/baoyu-skills
/plugin install baoyu-skills@baoyu-skills
```

### 方式 3: 直接告诉 Agent

> 请帮我安装 github.com/JimLiu/baoyu-skills 中的 Skills

## 核心工具

### baoyu-fetch

将 URL 转换为高质量 Markdown 或 JSON，使用 Chrome CDP 和站点适配器。

```bash
baoyu-fetch https://example.com
baoyu-fetch https://example.com --format markdown --output article.md --download-media
baoyu-fetch https://x.com/lennysan/status/2036483059407810640 --wait-for interaction
```

**依赖**: Chrome 浏览器 (通过 CDP)

**选项**:
- `--output <file>`: 保存输出到文件
- `--format <type>`: 输出格式 (markdown | json)
- `--download-media`: 下载媒体文件到 ./imgs 和 ./videos
- `--headless`: 启动无头 Chrome
- `--wait-for <mode>`: 等待模式 (interaction | force)
- `--cdp-url <url>`: 复用现有的 Chrome DevTools 端点

**注意**: 当前环境缺少 bun 运行时，无法直接执行。需要先安装 bun。

### 其他技能

共 22 个技能，分类如下：

- **内容技能**: baoyu-article-illustrator, baoyu-comic, baoyu-cover-image, baoyu-post-to-wechat, baoyu-post-to-weibo, baoyu-post-to-x
- **AI 生成技能**: baoyu-image-gen, baoyu-imagine, baoyu-diagram, baoyu-infographic
- **工具技能**: baoyu-compress-image, baoyu-format-markdown, baoyu-translate, baoyu-url-to-markdown, baoyu-xhs-images, baoyu-youtube-transcript

详细说明见 `[[Baoyu Skills]]` 主题页面。

## 技术架构

- **Monorepo**: 使用 npm workspaces 管理多个包
- **包结构**:
  - `packages/baoyu-chrome-cdp`: Chrome DevTools Protocol 客户端
  - `packages/baoyu-fetch`: URL 抓取工具 (CLI 入口)
  - `packages/baoyu-md`: Markdown 处理库
- **运行时**: bun (用于 TypeScript 直接执行)
- **依赖**: pdf-lib, pptxgenjs 等

## 当前状态

- ✅ 仓库已克隆到 `/tmp/baoyu-skills-test`
- ✅ npm 依赖已安装 (通过 `npm install` + workspaces)
- ✅ `skills` CLI 已安装 (v1.5.0)
- ✅ baoyu-skills 已通过 `skills add` 安装 (交互式)
- ✅ bun 已安装并配置完成 (v1.3.12)
- ✅ 技能通过 skills CLI 安装（22 个技能）
- 可通过 `bun packages/baoyu-fetch/src/cli.ts` 直接运行
- 已创建符号链接: /usr/local/bin/bun

## 参考文档

- 原始 README: `[[Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-README.md|Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-README.md]]`
- 更新日志: `[[Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-CHANGELOG.md|Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-CHANGELOG.md]]`
- Claude 集成说明: `[[Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-CLAUDE.md|Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-CLAUDE.md]]`
