---
title: Canvas美化
created: 2026-04-23
updated: 2026-04-23
type: note
category: tool-beautification
tool: Obsidian
topic: Canvas
source_name: PKMer 知识社区
source_type: 公众号
source_url: https://mp.weixin.qq.com/s/0mGSjOsnJl5ZA2H8TcVz3g
tags: [subscriptions, wechat, obsidian, canvas, tool-beautification]
aliases: [Obsidian Canvas美化]
---

# Canvas美化

这条收藏聚焦 `Obsidian / Canvas / 视觉主题`，来源是微信公众号内容沉淀，不再按公众号名单独命名。

## 来源标签

- 来源：PKMer 知识社区
- 类型：公众号
- 地址：[微信公众号原文](https://mp.weixin.qq.com/s/0mGSjOsnJl5ZA2H8TcVz3g)

## 来源信息

- 公众号：PKMer 知识社区
- 作者：熊猫别熬夜
- 文章标题：告别单调！10 套高颜值 Obsidian Canvas 配色方案分享
- 原文链接：[微信公众号原文](https://mp.weixin.qq.com/s/0mGSjOsnJl5ZA2H8TcVz3g)
- 发布时间：2026-04-15 22:48
- 地区：湖北

## 收藏原因

- 命中你关注的工具美化类内容
- 可以直接作用于 Obsidian Canvas 的视觉整理体验
- 后续同类内容适合继续并入这个主题页，而不是按公众号分散记录

## 内容摘要

这篇文章分享了适用于 Obsidian Canvas 的 10 套主题配色，强调：

- 适配浅色/深色模式
- 支持 Style Settings 中一键切换主题
- 可以开启卡片渐变背景
- 可以调整边框宽度和透明度
- 适合演示、知识整理和创意草图场景

## 归类

- 主方向：工具美化
- 细分：Obsidian / Canvas / 视觉主题
- 相关页面：[[Wiki百科/1. 实体/1.3 产品/obsidian.md|Obsidian]]
- 上级目录：[[个人存货/3. 技能树/3.1 订阅管理/Obsidian/README|Obsidian 订阅收藏]]

## JSON 整理版

> [!info]
> 文章正文里实际给的是一段 CSS Snippet + Style Settings 配置，不是标准 JSON。
> 下面这份是我根据文章内容整理出的 JSON 摘要版，方便后续复用。

```json
{
  "name": "Canvas-熊猫",
  "source_article": "告别单调！10 套高颜值 Obsidian Canvas 配色方案分享",
  "account": "PKMer 知识社区",
  "author": "熊猫别熬夜",
  "published_at": "2026-04-15 22:48",
  "kind": "obsidian-canvas-theme-config-summary",
  "style_settings": {
    "default_scheme": "canvas-schemes-rainbow",
    "schemes": [
      { "label": "Ob 默认", "value": "canvas-default" },
      { "label": "经典彩虹", "value": "canvas-schemes-rainbow" },
      { "label": "柔和渐变", "value": "canvas-schemes-soft" },
      { "label": "商务蓝", "value": "canvas-schemes-business" },
      { "label": "自然绿", "value": "canvas-schemes-nature" },
      { "label": "中国红", "value": "canvas-schemes-china-red" },
      { "label": "东方紫", "value": "canvas-schemes-purple" },
      { "label": "顶刊经典", "value": "canvas-schemes-classic" },
      { "label": "蓝色渐变系", "value": "canvas-schemes-blue" },
      { "label": "复古学术风", "value": "canvas-schemes-vintage" },
      { "label": "浪漫温柔系", "value": "canvas-schemes-romantic" },
      { "label": "马卡龙 pastel", "value": "canvas-schemes-macaron" }
    ],
    "card_gradient_toggle": true,
    "border_width": {
      "default": 1,
      "min": 0,
      "max": 10,
      "step": 0.5,
      "unit": "px"
    },
    "gradient_opacity": {
      "default": 0.6,
      "min": 0.1,
      "max": 1.0,
      "step": 0.05
    }
  }
}
```
