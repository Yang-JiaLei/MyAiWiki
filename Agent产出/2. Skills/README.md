---
标题: Agent Skills
创建时间: 2026-04-14 06:35:00
最后更新: 2026-04-14 06:35:00
标签: [skills, agent, tools, 能力]
类别: Agent产出
状态: 活跃
---

# Agent Skills 目录

记录和归档已安装的 Hermes Agent Skills。

## 概述

本目录用于存放和管理 Hermes Agent 已安装的各种 Skills。每个 Skill 都是一个独立的模块，提供特定的功能增强。

## 已安装的 Skills

### 1. **hv-analysis** ✅
- **功能**: 横纵分析法深度研究
- **作者**: KKKKhazix (数字生命卡兹克)
- **安装时间**: 2026-04-14
- **状态**: 已安装并可用
- **文档**: [[hv-analysis]]
- **仓库**: https://github.com/KKKKhazix/khazix-skills

### 2. **khazix-writer** ✅
- **功能**: 公众号长文写作（卡兹克风格）
- **作者**: KKKKhazix (数字生命卡兹克)
- **安装时间**: 2026-04-14
- **状态**: 已安装并可用
- **文档**: [[khazix-writer]]
- **仓库**: https://github.com/KKKKhazix/khazix-skills

## 技能目录结构

每个 Skill 都应该包含以下目录结构：

```
Skill名称/
├── SKILL.md           # 技能定义文档（必需）
├── references/        # 参考资料、模板、示例
├── scripts/          # 辅助脚本（可选）
└── README.md         # 技能说明（可选，可由SKILL.md生成）
```

## Skills 安装位置

Hermes Agent 的 Skills 安装路径：
```
~/.hermes/skills/
├── github-repo-ingestion/  # 内置技能
├── hv-analysis/           # 新增 - 深度研究
├── khazix-writer/         # 新增 - 公众号写作
└── prompts/               # 新增 - 提示词模板
```

## 如何安装新 Skill

### 方法1：手动安装
```bash
# 克隆技能仓库
git clone https://github.com/username/skill-repo.git

# 复制技能目录
cp -r skill-repo/skill-name ~/.hermes/skills/

# 验证安装
skill_view(name="skill-name")
```

### 方法2：使用 skill_manage 工具
```python
# 通过 Hermes 工具安装
skill_manage(action="create", name="skill-name", content="...")
```

## 技能分类

### 按功能分类
- **研究分析类**: hv-analysis - 深度研究分析
- **内容创作类**: khazix-writer - 写作生成
- **工具辅助类**: 待添加

### 按来源分类
- **官方内置**: github-repo-ingestion
- **第三方社区**: hv-analysis, khazix-writer
- **自定义开发**: 待创建

## 技能使用

### 自动触发
Skills 会根据用户输入自动触发：
- 用户说"帮我用横纵分析法研究一下" → 触发 `hv-analysis`
- 用户说"帮我写一篇公众号文章" → 触发 `khazix-writer`

### 手动调用
通过 `skill_view` 工具查看技能详情：
```bash
skill_view(name="hv-analysis")
skill_view(name="khazix-writer")
```

## 技能文档标准

每个 Skill 的 SKILL.md 应包含：

```yaml
---
name: skill-name
description: |
  简要描述技能的功能和使用场景
  触发词列表
  不适用场景说明
---
# 技能详细文档
## 使用方法
## 参数说明
## 示例
## 注意事项
```

## 技能开发指南

### 开发流程
1. **设计技能功能** - 明确技能要解决什么问题
2. **编写 SKILL.md** - 按照标准格式编写技能定义
3. **实现脚本逻辑** - 编写必要的辅助脚本
4. **准备参考资料** - 收集参考文档和模板
5. **测试验证** - 在实际场景中测试
6. **文档完善** - 补充使用说明和示例

### 最佳实践
- 单一职责：一个技能只做一件事
- 明确触发：清晰定义触发条件和词
- 完整文档：提供详细的使用说明
- 可复用性：设计通用的解决方案

## 维护记录

| 技能 | 版本 | 安装日期 | 最后更新 | 状态 |
|------|------|---------|---------|------|
| hv-analysis | main | 2026-04-14 | 2026-04-14 | ✅ 正常 |
| khazix-writer | main | 2026-04-14 | 2026-04-14 | ✅ 正常 |

## 相关链接

- [[技能树]] - 个人技能发展路线
- [[Agent 配置]] - Agent 配置管理
- [[工具使用记录]] - 工具使用历史

## 待办事项

- [ ] 测试 hv-analysis 的PDF生成功能
- [ ] 测试 khazix-writer 的写作风格
- [ ] 添加更多第三方技能
- [ ] 开发自定义技能
- [ ] 建立技能使用统计

---

**更新记录**:
- 2026-04-14：初始创建，安装 hv-analysis 和 khazix-writer
- 安装来源: https://github.com/KKKKhazix/khazix-skills