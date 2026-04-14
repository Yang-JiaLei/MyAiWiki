---
标题: hv-analysis
创建时间: 2026-04-14 06:35:00
最后更新: 2026-04-14 06:35:00
标签: [skill, 横纵分析法, 深度研究, 分析框架, 工具]
类型: Agent Skill
状态: 已安装
作者: KKKKhazix (数字生命卡兹克)
仓库: https://github.com/KKKKhazix/khazix-skills
安装路径: ~/.hermes/skills/hv-analysis/
技能类型: 深度研究
---

# hv-analysis Skill

横纵分析法（Horizontal-Vertical Analysis）深度研究 Skill，由数字生命卡兹克提出。

## 概述

这是一个系统性的深度研究框架，融合了：
- 语言学中的历时-共时分析（索绪尔）
- 社会科学的纵向-横截面研究设计
- 商学院案例研究法
- 竞争战略分析

核心思想：**纵向追时间深度，横向追同期广度，最终交汇出判断**。

## 核心功能

### 双轴分析框架
1. **纵轴（时间深度）**：
   - 追踪研究对象的完整生命历程
   - 从诞生到当下的发展轨迹
   - 以叙事故事形式呈现

2. **横轴（竞争广度）**：
   - 在当下时间截面的系统性横向对比
   - 竞品识别和分析
   - 市场份额和用户口碑对比

3. **交叉分析**：
   - 两条轴交汇产出独到洞察
   - 形成最终判断和建议

### 自动研究流程
- 自动联网收集信息
- 并行搜索策略（3个子Agent）
- 系统性信息整理
- 排版精美的PDF报告输出

## 使用场景

### 适用场景
- 产品深度研究
- 公司分析
- 概念/技术调研
- 人物研究
- 竞品分析
- 市场调研

### 触发词
- "横纵分析"
- "研究一下"
- "帮我分析"
- "深度研究"
- "做个研究"
- "调研一下"
- "竞品分析"
- "帮我看看这个产品/公司/概念"
- "帮我摸清楚"
- "帮我搞懂"
- "帮我做个deep research"

### 不适用场景
- 简单名词解释（"XX是什么"）
- 公众号写作（用 khazix-writer）
- 纯标题摘要生成（用 wechat-title）

## 安装信息

### 安装方式
已通过手动安装方式部署：
```bash
cp -r /tmp/khazix-skills/hv-analysis ~/.hermes/skills/
```

### 目录结构
```
~/.hermes/skills/hv-analysis/
├── SKILL.md           # 技能定义文件（19722 bytes）
├── references/        # 参考资料目录
└── scripts/          # 工具脚本目录
    └── md_to_pdf.py  # Markdown转PDF脚本
```

### 依赖要求
```bash
pip install weasyprint markdown --break-system-packages
```

## 使用方法

### 基本用法
```
用户: 帮我用横纵分析法研究一下 Hermes Agent
Agent: [自动触发 hv-analysis skill]
```

### 输出格式
最终输出为排版精美的PDF研究报告，包含：
1. 执行摘要
2. 纵向分析（时间线）
3. 横向对比（竞品矩阵）
4. 交叉洞察
5. 结论与建议

## 工作流程

### 第一步：明确研究对象
- 确认研究对象（产品/公司/概念/人物）
- 确定研究类型
- 了解研究动机
- 识别特别关注点

### 第二步：并行信息收集
- 子Agent 1：纵向信息（起源、发展、关键事件）
- 子Agent 2：横向信息（竞品、对比、市场份额）
- 子Agent 3：补充信息（社区讨论、深度背景）

### 第三步：整合分析
- 信息整合和验证
- 纵向时间线梳理
- 横向对比分析
- 交叉点洞察提炼

### 第四步：报告生成
- Markdown格式报告
- PDF排版转换
- 最终交付

## 相关技能

- [[khazix-writer]] - 公众号长文写作技能
- [[wechat-title]] - 标题摘要生成技能

## 作者信息

**数字生命卡兹克（Khazix）**
- GitHub: [KKKKhazix](https://github.com/KKKKhazix)
- 公众号：数字生命卡兹克
- 使命：激发大家对AI的好奇

## 参考资源

- 原始仓库：https://github.com/KKKKhazix/khazix-skills
- Skill文档：`hv-analysis/SKILL.md`
- 安装指南：README.md

## 更新记录

- 2026-04-14：初始安装版本
- 版本：main 分支最新（c6d097b）

---

**提示**: 这是一个重量级Skill，需要联网搜索和PDF生成能力。确保系统已安装 `weasyprint` 和 `markdown` 依赖。