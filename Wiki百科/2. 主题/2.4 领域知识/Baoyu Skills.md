---
名称: Baoyu Skills
类别: 工具集
标签: [claude-code, skills, ai, automation, content-generation, image-generation]
---

# Baoyu Skills 总览

由 [JimLiu](https://github.com/jimliu) 开发的 Claude Code 技能集合，提供 22 个技能，涵盖内容创作、AI 生成、文档处理和社交发布等场景。

## 技能分类

### 内容技能 (Content Skills)

用于内容生成和发布的技能。

| 技能 | 说明 | 主要功能 |
|------|------|----------|
| [[baoyu-article-illustrator]] | 文章配图生成 | 为文章自动生成插图 |
| [[baoyu-comic]] | 漫画生成 | 创建漫画和分镜 |
| [[baoyu-cover-image]] | 封面图生成 | 生成文章/视频封面 |
| [[baoyu-post-to-wechat]] | 微信发布 | 将内容发布到微信公众号 |
| [[baoyu-post-to-weibo]] | 微博发布 | 发布到微博 |
| [[baoyu-post-to-x]] | X (Twitter) 发布 | 发布到 X 平台 |

### AI 生成技能 (AI Generation Skills)

利用 AI 模型生成图像和图表。

| 技能 | 说明 | 后端 |
|------|------|------|
| [[baoyu-image-gen]] | 图像生成 | 多模型支持 |
| [[baoyu-imagine]] | AI 绘图 | DALL-E/Stable Diffusion |
| [[baoyu-diagram]] | 图表生成 | Mermaid, Graphviz |
| [[baoyu-infographic]] | 信息图生成 | 数据可视化 |

### 工具技能 (Utility Skills)

实用工具和格式转换。

| 技能 | 说明 | 依赖 |
|------|------|------|
| [[baoyu-compress-image]] | 图片压缩 | 无损/有损压缩 |
| [[baoyu-format-markdown]] | Markdown 格式化 | 规范化和美化 |
| [[baoyu-translate]] | 翻译 | 多语言支持 |
| [[baoyu-url-to-markdown]] | URL 转 Markdown | 基于 [[baoyu-fetch]] |
| [[baoyu-xhs-images]] | 小红书图片处理 | 水印移除、裁剪 |
| [[baoyu-youtube-transcript]] | YouTube 字幕 | 提取和翻译 |

### 特殊技能

| 技能 | 说明 | 警告 |
|------|------|------|
| [[baoyu-danger-gemini-web]] | Gemini Web 集成 | 实验性功能 |
| [[baoyu-danger-x-to-markdown]] | X 内容转 Markdown | 违反 ToS 风险 |

## 核心组件

### baoyu-fetch

**核心工具**：将任意 URL 抓取为 Markdown 或 JSON。

**特性**:
- 使用 Chrome DevTools Protocol (CDP) 进行真实浏览器渲染
- 支持登录态保持和交互等待
- 自动适配主流站点（Twitter/X、知乎、微信公众号等）
- 可下载媒体资源并重写链接

**使用示例**:
```bash
baoyu-fetch https://example.com
baoyu-fetch https://x.com/user/status/123 --wait-for interaction
```

**依赖**: Chrome 浏览器 + bun 运行时

### baoyu-chrome-cdp

Chrome DevTools Protocol 客户端，为 baoyu-fetch 提供浏览器控制能力。

### baoyu-md

Markdown 处理库，提供解析、转换和优化功能。

## 安装与配置

### 前置要求

- Node.js 环境
- Chrome 浏览器 (用于 baoyu-fetch)
- bun 运行时 (可选，用于直接执行 TS)
- skills CLI: `npm install -g skills`

### 安装命令

```bash
skills add jimliu/baoyu-skills
```

或通过 Claude Code 插件市场:
```
/plugin marketplace add JimLiu/baoyu-skills
/plugin install baoyu-skills@baoyu-skills
```

### 环境变量

- `BAOYU_CHROME_PROFILE_DIR`: Chrome 用户数据目录
- `CHROME_PATH`: Chrome 可执行文件路径

## 与 Wiki 系统的集成

这些技能可以与本地知识库配合使用：

1. **URL 保存**: 使用 `baoyu-fetch` 将文章转为 Markdown，保存到 `Wiki百科/3. 原始来源/` 目录（待细化）
2. **图片处理**: 使用 `baoyu-compress-image` 优化图片后再插入笔记
3. **图表生成**: 使用 `baoyu-diagram` 生成 Mermaid 图表嵌入文档
4. **内容发布**: 使用 `baoyu-post-to-*` 将笔记发布到社交平台

## 相关链接

- 项目仓库: https://github.com/jimliu/baoyu-skills
- 安装文档: `[[Wiki百科/1. 实体/1.4 工具/baoyu-skills.md|Wiki百科/1. 实体/1.4 工具/baoyu-skills.md]]`
- 原始文档: `[[Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-README.md|Wiki百科/3. 原始来源/3.1 文章/baoyu-skills-README.md]]`
