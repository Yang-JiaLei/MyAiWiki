---
title: install-hermes-skill-from-github Skill
created: 2026-04-14 06:45:00
updated: 2026-04-15
type: report
category: agent-skills
tags: [skill, install, github, hermesskill, 部署]
status: 已记录
skill_type: 系统集成
---

# install-hermes-skill-from-github Skill

用于从 GitHub 仓库安装第三方 Hermes Agent Skill 的标准操作流程技能。

## 概述

这是一个**元技能（meta-skill）**，记录了如何将第三方 Skill 安装到 Hermes Agent 的完整方法论。

它不是直接执行任务的 Skill，而是**指导如何安装其他 Skills 的文档化流程**。

## 核心价值

### 为什么需要这个 Skill
1. **标准化流程** - 避免每次安装都重新摸索
2. **降低错误率** - 提供检查清单和验证步骤
3. **知识沉淀** - 将安装经验转化为可复用的知识
4. **团队共享** - 让其他人也能正确安装 Skills

### 适用场景
- 安装任何从 GitHub 发布的 Hermes Skill
- 批量部署多个第三方 Skills
- 向团队传授 Skill 安装方法
- 建立 CI/CD 自动化安装流程

## 安装流程（5阶段）

### Phase 1: 发现与评估
```
1. 获取 Skill 仓库 URL
2. 检查活跃度（commit 频率、issue 响应）
3. 阅读 SKILL.md 了解功能和依赖
4. 确认兼容性和需求匹配
```

### Phase 2: 环境准备
```bash
# 克隆到临时目录
cd /tmp
git clone <skill-repo-url>

# 检查结构
ls -la <skill-repo>/
# 预期: SKILL.md + references/ + scripts/
```

### Phase 3: 安装部署
```bash
# 复制到 Skills 目录
cp -r /tmp/<skill-repo>/<skill-name> ~/.hermes/skills/

# 安装 Python 依赖
pip install <dependencies> --break-system-packages

# 设置权限
chmod -R 755 ~/.hermes/skills/<skill-name>/
```

### Phase 4: 验证测试
```bash
# 检查安装
ls -la ~/.hermes/skills/<skill-name>/

# 验证依赖
python3 -c "import <module>; print('OK')"

# 运行测试脚本（如有）
python3 ~/.hermes/skills/<skill-name>/scripts/test.py
```

### Phase 5: 文档化
- 创建 Wiki 实体页面
- 更新 Skills 目录 README
- 编写安装日志
- 更新知识库索引

## 实际应用案例

### 案例1: 安装 khazix-skills (2026-04-14)

#### 背景
从 https://github.com/KKKKhazix/khazix-skills 安装 2 个 Skills。

#### 执行过程
```
1. 克隆: git clone https://github.com/KKKKhazix/khazix-skills.git
2. 发现: hv-analysis, khazix-writer, prompts 三个目录
3. 复制: cp -r 每个目录 ~/.hermes/skills/
4. 依赖: pip install weasyprint markdown
5. 测试: md_to_pdf.py 生成 PDF 成功 (15KB)
6. 文档: 创建 4 个文档页面，更新索引
```

#### 成果
- ✅ hv-analysis 安装成功（依赖已配置）
- ✅ khazix-writer 安装成功（无依赖）
- ✅ 知识库完整记录
- ✅ 51+ 页面更新

#### 学到的经验
1. **依赖识别**：从 SKILL.md 和脚本的 import 语句识别依赖
2. **测试必要性**：即使文档说无依赖，也要实际验证
3. **文档同步**：安装后立即更新知识库，避免遗忘
4. **权限检查**：确保脚本有执行权限

### 案例2: 待应用
（未来安装其他 Skill 时复用此流程）

## 关键检查清单

### 安装前 ✅
- [ ] Skill 仓库 URL 正确
- [ ] 最近有更新（非废弃项目）
- [ ] SKILL.md 内容完整
- [ ] 触发词定义清晰
- [ ] 依赖列表明确
- [ ] Hermes 版本兼容

### 安装中 ✅
- [ ] 文件完整复制
- [ ] 依赖全部安装
- [ ] 脚本权限正确（755）
- [ ] 配置文件格式正确

### 安装后 ✅
- [ ] Skill 能被识别
- [ ] 触发词能触发
- [ ] 功能输出正常
- [ ] 无依赖错误
- [ ] 文档已创建
- [ ] 索引已更新

## 故障排除指南

| 问题 | 可能原因 | 解决方案 |
|------|---------|---------|
| Skill 不触发 | 触发词不匹配 | 检查 SKILL.md 中的触发词列表 |
| 导入错误 | 依赖缺失 | `pip install <missing-package>` |
| 脚本失败 | 权限不足 | `chmod +x scripts/*.py` |
| PDF 生成失败 | 字体缺失 | 安装中文字体 `apt-get install fonts-noto-cjk` |
| 文件找不到 | 路径错误 | 检查 `~/.hermes/skills/` 路径 |

## 技能输出格式

### 标准文档结构
每个通过此流程安装的 Skill 应在知识库中生成：

```
Wiki百科/1. 实体/1.4 工具/
├── <skill-name>.md           # 技能实体页面

Agent产出/3. Skills/
├── README.md                 # 目录总览（更新）
├── 技能总览.md              # 所有技能对比
└── 安装日志.md              # 详细安装记录（更新）
```

### 实体页面模板
```markdown
---
标题: <Skill名称>
创建时间: <date>
标签: [skill, <category>]
类型: Agent Skill
状态: 已安装
作者: <作者>
仓库: <GitHub URL>
安装路径: ~/.hermes/skills/<skill-name>/
技能类型: <类型>
---

# <Skill名称>

## 概述
[功能描述]

## 安装信息
- 安装方式: 通过 install-hermes-skill-from-github 流程
- 安装日期: <date>
- 依赖: <依赖列表>

## 使用方法
[使用说明]

## 相关链接
- 安装日志: [[安装日志]]
```

## 与相关技能的关系

### 依赖关系
此 Skill **不依赖**其他 Skills，但用于安装其他 Skills。

### 相似技能
- **github-repo-ingestion**: 官方内置，用于仓库同步
- **npm-cli-auth-investigation**: 调查工具认证机制
- **本 Skill**: 标准化第三方 Skill 安装流程

## 维护与更新

### 流程改进
当发现更好的安装方法时：
1. 更新 SKILL.md 中的流程描述
2. 记录新发现的问题和解决方案
3. 更新检查清单

### 版本记录
- v1.0.0 (2026-04-14): 基于 khazix-skills 安装经验创建

## 相关链接

- **实践案例**: [[安装日志]] (khazix-skills 安装记录)
- **已安装技能**: [[hv-analysis]], [[khazix-writer]]
- **Skill 目录**: `~/.hermes/skills/`
- **Hermes 文档**: `~/.hermes/`

## 快速参考

### 一键安装命令模板
```bash
# 1. 克隆
cd /tmp && git clone <REPO_URL>

# 2. 复制
cp -r /tmp/<repo>/<skill> ~/.hermes/skills/

# 3. 安装依赖
pip install <dependencies> --break-system-packages

# 4. 验证
python3 -c "import <module>"

# 5. 清理
rm -rf /tmp/<repo>
```

### 检查清单文件
保存为 `~/.hermes/skill-install-checklist.md` 供每次安装时使用。

---

**技能类型**: 方法论 / 流程指导
**复用性**: 高（适用于所有第三方 Skill 安装）
**维护频率**: 低（流程稳定，偶尔更新）
**最后验证**: 2026-04-14 (khazix-skills 安装)
