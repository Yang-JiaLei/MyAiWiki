---
title: prompts.chat
created: 2026-04-13 05:25:00
updated: 2026-04-15
type: entity
category: projects
tags: [prompt, 提示词, 开源, AI, 工具]
status: 活跃
github: https://github.com/f/prompts.chat
website: https://prompts.chat
---

# prompts.chat

世界上最大的开源AI提示词库，原名 Awesome ChatGPT Prompts。

## 概述

prompts.chat 是一个开源的提示词库项目，收集和整理了大量的AI提示词，支持 ChatGPT、Claude、Gemini、Llama、Mistral 等多种AI模型。

## 项目特点

### 核心特性
1. **大规模收集**：包含数千个高质量的提示词
2. **开源免费**：完全开源，可自由使用和贡献
3. **多模型支持**：适用于各种主流AI模型
4. **社区驱动**：由全球开发者共同维护

### 技术架构
- **前端**：Next.js + TypeScript
- **数据库**：PostgreSQL + Prisma
- **部署**：Vercel + Docker
- **数据格式**：CSV + Markdown

## 数据格式

### CSV格式 (prompts.csv)
主要数据存储格式，包含以下列：
- `act`：角色/场景名称
- `prompt`：完整的提示词内容
- `for_devs`：是否为开发者相关
- `type`：提示词类型（TEXT）
- `contributor`：贡献者

### Markdown格式 (PROMPTS.md)
完整的提示词文档，按类别组织。

## 使用方式

### 在线使用
1. **浏览网站**：https://prompts.chat
2. **搜索提示词**：按类别、标签搜索
3. **复制使用**：直接复制提示词到AI对话

### 本地使用
1. **克隆仓库**：
   ```bash
   git clone https://github.com/f/prompts.chat.git
   ```

2. **使用数据**：
   ```bash
   # 使用CSV文件
   cat prompts.csv | grep "Linux Terminal"
   
   # 使用Markdown文件
   grep -n "Linux Terminal" PROMPTS.md
   ```

### 自托管
```bash
npx prompts.chat new my-prompt-library
cd my-prompt-library
npm install && npm run setup
```

## 项目影响

### 社区认可
- **GitHub Stars**：160k+
- **Forbes报道**：被福布斯杂志报道
- **学术引用**：40+篇学术论文引用
- **高校使用**：哈佛、哥伦比亚等高校参考

### 行业影响
- **AI先驱认可**：OpenAI、Hugging Face创始人推荐
- **开发者喜爱**：最受欢迎的提示词数据集
- **企业采用**：多家科技公司内部使用

## 与个人Prompt库的关系

我的[[个人Prompt库]]项目参考了 prompts.chat 的以下方面：

### 借鉴的设计
1. **数据格式**：采用类似的CSV结构
2. **分类体系**：参考其提示词分类方式
3. **社区模式**：学习其开源协作模式

### 个性化改进
1. **中文优化**：所有提示词中文化
2. **分类细化**：更细致的分类体系
3. **效果跟踪**：添加使用效果评估
4. **集成优化**：与Obsidian深度集成

## 贡献指南

### 添加新提示词
1. 访问 https://prompts.chat/prompts/new
2. 填写提示词信息
3. 提交后自动同步到GitHub

### 代码贡献
1. Fork 项目仓库
2. 创建功能分支
3. 提交Pull Request
4. 通过代码审查

## 相关项目

### 类似项目
- [[Awesome ChatGPT Prompts]] - 前身项目
- [[Prompt Engineering Guide]] - 提示词工程指南
- [[OpenAI Cookbook]] - OpenAI官方示例

### 衍生项目
- [[个人Prompt库]] - 基于此项目的个人化版本
- [[企业Prompt库]] - 企业级提示词管理系统

## 技术栈

### 核心依赖
- **框架**：Next.js 14
- **语言**：TypeScript
- **数据库**：PostgreSQL
- **ORM**：Prisma
- **样式**：Tailwind CSS

### 开发工具
- **测试**：Vitest + Playwright
- **代码质量**：ESLint + Prettier
- **部署**：Vercel + Docker
- **监控**：Sentry

## 学习资源

### 官方文档
- [GitHub README](https://github.com/f/prompts.chat)
- [自托管指南](https://prompts.chat/docs/self-hosting)
- [API文档](https://prompts.chat/docs/api)

### 教程文章
- [如何贡献提示词](https://prompts.chat/docs/contributing)
- [提示词工程指南](https://prompts.chat/book)
- [企业部署指南](https://prompts.chat/docs/enterprise)

## 统计信息

- **提示词数量**：6,000+
- **贡献者数量**：1,000+
- **月活跃用户**：100万+
- **GitHub Stars**：160k+
- **创建时间**：2022年12月

## 未来规划

### 短期目标
1. 增加多语言支持
2. 优化搜索功能
3. 改进移动端体验

### 长期愿景
1. 建立提示词质量标准
2. 开发高级提示词编辑器
3. 构建提示词市场生态

---

**参考**: 本项目是[[个人Prompt库]]的主要参考来源，提供了成熟的开源提示词库架构和实践经验。
