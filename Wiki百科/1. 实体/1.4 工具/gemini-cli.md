---
title: gemini-cli
type: tool
category: CLI
official: true
developer: Google
language: TypeScript/JavaScript
license: Apache-2.0
repo: https://github.com/google-gemini/gemini-cli
npm: https://www.npmjs.com/package/@google/gemini-cli
docs: https://github.com/google-gemini/gemini-cli
install:
  - npm install -g @google/gemini-cli
  - 版本: 0.37.1
  - 验证: gemini --version
related:
  - [[Gemini]]
  - [[Google AI Studio]]
  - [[Wiki百科/2. 主题/2.3 方法论/Prompt Engineering.md]]
  - [[prompts-chat|prompts.chat]]
---

# gemini-cli

Google 官方发布的 Gemini 命令行客户端，支持与 Gemini 模型进行交互、文件上传、MCP 服务器管理等。

## 安装

```bash
npm install -g @google/gemini-cli
gemini --version  # 验证安装
```

**版本:** 0.37.1（截至 2026-04 记录）

## 认证方式

gemini-cli 支持两种认证方式，根据使用环境选择：

### 方式一：API Key（推荐用于服务器/无浏览器环境）

1. 访问 [Google AI Studio API Key 页面](https://aistudio.google.com/apikey)
2. 创建 API 密钥
3. 设置环境变量：

```bash
export GEMINI_API_KEY=你的API密钥
```

4. 运行 `gemini` 即可使用

**优点：** 无需浏览器，适合 CI/CD、服务器、容器环境。

### 方式二：OAuth（适用于本地桌面环境）

gemini-cli 使用 Google OAuth 2.0 进行身份验证：

- **OAuth 客户端 ID:** `681255809395-oo8ft2oprdrnp9e3aqf6av3hmdib135j.apps.googleusercontent.com`
- **授权范围:** `https://www.googleapis.com/auth/cloud-platform`
- **回调地址:** `http://127.0.0.1:{随机端口}/oauth2callback`
- **流程:**
  1. CLI 启动本地 HTTP 服务器（随机端口）
  2. 生成 OAuth URL 并在浏览器中打开
  3. 用户授权后，Google 重定向到本地回调
  4. 服务器捕获授权码，交换访问令牌
  5. 令牌保存在本地（加密存储）

**限制：** 需要图形界面浏览器，在无界面的服务器环境无法完成。

#### OAuth 环境变量

- `NO_BROWSER=true` — 禁用自动打开浏览器，URL 会打印到输出中（但仍需手动完成回调，不推荐）
- `OAUTH_CALLBACK_HOST` — 回调服务器监听地址，默认 `127.0.0.1`
- `OAUTH_CALLBACK_PORT` — 指定回调端口（默认随机选择可用端口）

#### 为何 OAuth 不适用于服务器

在无图形界面的 Linux 服务器环境：
- 无法自动打开浏览器
- 即使手动复制 URL 授权，本地回调服务器仍在运行，但用户无法轻易完成 OAuth 流程的交互
- 官方推荐使用 API Key

## 配置

配置文件位置：`~/.gemini/settings.json`

示例配置：

```json
{
  "model": {
    "provider": "google-genai",
    "model": "gemini-2.5-pro"
  }
}
```

**注意：** `model` 字段必须为对象格式（包含 `provider` 和 `model`），字符串格式会导致错误。

## 基本使用

```bash
# 交互模式（启动后输入问题）
gemini

# 单次查询
gemini "解释什么是量子计算"

# 上传文件并提问
gemini -f document.pdf "总结这份文档"

# 指定模型
gemini --model gemini-2.0-flash "你的问题"
```

## 功能特性

- **交互式对话:** 默认启动 REPL 模式，支持多轮对话
- **文件上传:** 支持 PDF、图片、文本等多种格式
- **MCP 服务器管理:** `gemini mcp` 子命令添加、管理 MCP 服务
- **扩展系统:** 支持安装社区扩展（extensions）
- **技能（Skills）:** 管理和使用自定义技能
- **钩子（Hooks）:** 自定义命令和自动化
- **多模态:** 支持图像、音频、视频输入

## 与 Wiki 系统的集成

本知识库已将 gemini-cli 纳入管理：

- **实体页面:** [[Wiki百科/1. 实体/1.4 工具/gemini-cli.md]]（本页）
- **主题页面:** [[Gemini]] — 模型系列、能力概述
- **原始资料:** [[Wiki百科/3. 原始来源/书籍/gemini-cli-README.md]]
- **相关工具:** [[Wiki百科/1. 实体/1.5 项目/prompts-chat.md|prompts.chat]] — Prompt 工程资源

## 故障排查

### 认证失败

- 确认 `GEMINI_API_KEY` 已正确设置：`echo $GEMINI_API_KEY`
- API Key 需从 [Google AI Studio](https://aistudio.google.com/apikey) 获取
- 若使用 OAuth，确保本地端口未被占用，且可访问 `127.0.0.1`

### 无法打开浏览器

- 设置 `NO_BROWSER=true` 查看打印的 URL
- 在服务器环境，直接使用 API Key 认证

### 配置文件错误

- 检查 `~/.gemini/settings.json` 格式
- 确保 `model` 为对象：`{"provider":"google-genai","model":"gemini-2.5-pro"}`

## 更新日志

- **2026-04-12** 安装 gemini-cli 0.37.1，创建本页面，记录 OAuth 分析和 API Key 推荐方案

## 待办任务

- [ ] 实测 API Key 认证流程
- [ ] 录制 gemini-cli 使用示例视频
- [ ] 整理常用 Prompt 模板到 [[Wiki百科/2. 主题/2.3 方法论/Prompt Engineering.md]]
