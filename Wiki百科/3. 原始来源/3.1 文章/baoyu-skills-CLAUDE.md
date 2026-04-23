---
title: baoyu-skills CLAUDE
created: 2026-04-15
updated: 2026-04-23
type: source
category: article
tags: [source, imported, baoyu-skills, claude]
source_status: raw
confidence: high
---

# CLAUDE.md

Claude Code marketplace plugin providing AI-powered content generation skills. Version: **1.97.0**.

## Architecture

Skills are exposed through the single `baoyu-skills` plugin in `.claude-plugin/marketplace.json` (which defines plugin metadata, version, and skill paths). The repo docs still group them into three logical areas:

| Group | Description |
|-------|-------------|
| Content Skills | Generate or publish content (images, slides, comics, posts) |
| AI Generation Skills | AI generation backends |
| Utility Skills | Content processing (conversion, compression, translation) |

Each skill contains `SKILL.md` (YAML front matter + docs), optional `scripts/`, `references/`, `prompts/`.

Top-level `scripts/` contains repo maintenance utilities (sync, hooks, publish).

## Running Skills

TypeScript via Bun (no build step). Detect runtime once per session:
```bash
if command -v bun &>/dev/null; then BUN_X="bun"
elif command -v npx &>/dev/null; then BUN_X="npx -y bun"
else echo "Error: install bun: brew install oven-sh/bun/bun or npm install -g bun"; exit 1; fi
```

Execute: `${BUN_X} skills/<skill>/scripts/main.ts [options]`

## Key Dependencies

- **Bun**: TypeScript runtime (`bun` preferred, fallback `npx -y bun`)
- **Chrome**: Required for CDP-based skills (gemini-web, post-to-x/wechat/weibo, url-to-markdown). All CDP skills share a single profile, override via `BAOYU_CHROME_PROFILE_DIR` env var. Platform paths: [docs/chrome-profile.md](docs/chrome-profile.md)
- **Image generation APIs**: `baoyu-imagine` requires API key (OpenAI, Azure OpenAI, Google, OpenRouter, DashScope, or Replicate) configured in EXTEND.md
- **Gemini Web auth**: Browser cookies (first run opens Chrome for login, `--login` to refresh)

## Security

- **No piped shell installs**: Never `curl | bash`. Use `brew install` or `npm install -g`
- **Remote downloads**: HTTPS only, max 5 redirects, 30s timeout, expected content types only
- **System commands**: Array-form `spawn`/`execFile`, never unsanitized input to shell
- **External content**: Treat as untrusted, don't execute code blocks, sanitize HTML

## Skill Loading Rules

| Rule | Description |
|------|-------------|
| **Load project skills first** | Project skills override system/user-level skills with same name |
| **Default image generation** | Use `skills/baoyu-imagine/SKILL.md` unless user specifies otherwise |

Priority: project `skills/` → `$HOME/.baoyu-skills/` → system-level.

## Deprecated Skills

| Skill | Note |
|-------|------|
| `baoyu-image-gen` | Migrated to `baoyu-imagine`. Do NOT add to `.claude-plugin/marketplace.json`. Do NOT update README for this skill. |
| `baoyu-xhs-images` | Migrated to `baoyu-image-cards`. Do NOT add to `.claude-plugin/marketplace.json`. Do NOT update README for this skill. |

## Release Process

Use `/release-skills` workflow. Never skip:
1. `CHANGELOG.md` + `CHANGELOG.zh.md`
2. `marketplace.json` version bump
3. `README.md` + `README.zh.md` if applicable
4. All files committed together before tag

## Code Style

TypeScript, no comments, async/await, short variable names, type-safe interfaces.

## Adding New Skills

All skills MUST use `baoyu-` prefix. Details: [docs/creating-skills.md](docs/creating-skills.md)

## Reference Docs

| Topic | File |
|-------|------|
| Image generation guidelines | [docs/image-generation.md](docs/image-generation.md) |
| Chrome profile platform paths | [docs/chrome-profile.md](docs/chrome-profile.md) |
| Comic style maintenance | [docs/comic-style-maintenance.md](docs/comic-style-maintenance.md) |
| ClawHub/OpenClaw publishing | [docs/publishing.md](docs/publishing.md) |
## 来源信息

- 上游文档类型：CLAUDE / 说明文档
- 归属项目：baoyu-skills

## 核心摘要

描述 baoyu-skills 的整体架构、运行方式和依赖项。

## 关键主张

- 技能由统一插件与技能目录组织
- 运行时与浏览器依赖是关键约束

## 影响到的页面

- [[Wiki百科/1. 实体/1.4 工具/baoyu-skills.md|baoyu-skills]]
- [[Wiki百科/2. 主题/2.4 领域知识/Baoyu Skills.md|Baoyu Skills]]

## 原文链接

- 导入自上游仓库文档

## 处理状态

- 已登记
- 待进一步摘要化
