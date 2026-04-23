---
title: gemini-cli
created: 2026-04-15
updated: 2026-04-23
type: entity
category: tools
official: true
developer: Google
language: TypeScript/JavaScript
license: Apache-2.0
repo: https://github.com/google-gemini/gemini-cli
npm: https://www.npmjs.com/package/@google/gemini-cli
docs: https://www.geminicli.com/docs/
tags: [gemini, cli, google, ai, terminal]
---

# gemini-cli

Google 官方发布的 Gemini 命令行客户端，适合在终端中与 Gemini 模型交互、处理文件和接入自动化工作流。

## 是什么

`gemini-cli` 是面向开发者的终端优先 AI Agent 工具。它把 Gemini 能力带进 shell，适合做单次查询、交互式会话、文件处理和脚本化集成。

## 关键事实

- 官方仓库：<https://github.com/google-gemini/gemini-cli>
- 包名：`@google/gemini-cli`
- 安装方式：`npm install -g @google/gemini-cli`
- 常见认证方式：`GEMINI_API_KEY` 或本地 OAuth
- 能力范围：交互式问答、文件输入、内置工具、MCP 扩展

## 安装

```bash
npm install -g @google/gemini-cli
gemini --version
```

## 常见用法

```bash
# 进入交互模式
gemini

# 单次提问
gemini "解释什么是量子计算"

# 基于文件提问
gemini -f document.pdf "总结这份文档"
```

## 认证与配置

### API Key

推荐在服务器、CI 或无图形界面的环境中使用：

```bash
export GEMINI_API_KEY=your-key
```

### OAuth

适合本地图形界面环境。首次登录时通常会打开浏览器完成授权。

### 设置文件

配置文件通常位于 `~/.gemini/settings.json`，模型配置常见写法如下：

```json
{
  "model": {
    "provider": "google-genai",
    "model": "gemini-2.5-pro"
  }
}
```

## 相关主题

- [[Wiki百科/2. 主题/2.4 领域知识/Gemini.md|Gemini]]
- [[Wiki百科/2. 主题/2.3 方法论/Prompt Engineering.md|Prompt Engineering]]

## 相关来源

- [[Wiki百科/3. 原始来源/3.1 文章/gemini-cli-README.md|Gemini CLI README]]

## 待验证点

- CLI 的默认模型、授权流程和扩展机制是否已经变化
- 官方文档域名和安装说明是否有进一步迁移
