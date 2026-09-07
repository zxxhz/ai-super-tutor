# AI 超级私教（ai-super-tutor）· 可移植技能包

一份自包含、可分发、能安装进任意支持 `SKILL.md` 规范的 Agent（TRAE / Claude Code / Cursor 等）的通用认知学习辅导技能。

## 包内容

| 文件 | 作用 |
|---|---|
| `SKILL.md` | 技能本体（唯一必需文件），纯提示词驱动，无外部依赖 |
| `LICENSE.txt` | MIT 开源授权 |
| `manifest.json` | 包清单：名称/版本/安装步骤 |
| `README.md` | 本说明 |

## 为什么通用、科学、深度

- **零外部依赖**：纯提示词架构，兼容任何现代 Agent 环境。
- **全学科通用**：打破代码偏见，覆盖概念、自然科学、经济管理、外语文理与业务逻辑等各类学科。
- **事实标尺与防死锁**：支持粘贴讲义、文件路径引用；无资料时由 AI 快速生成权威共识大纲供用户确认，顺畅开启学习。
- **学习资产持久化**：自动在工作区维护 `learning-notes.md`，沉淀知识盲区与错题本。
- **成长型思维过程反馈**：拒绝廉价谄媚，推行 Process Praise，具体肯定推导逻辑与因果自洽。
- **艾宾浩斯复习排期**：终局输出 +1d / +3d / +7d 动作指引，打通长期记忆。
- **双重编码图解**：支持 Mermaid 流程图与 ASCII 概念结构图。

## 安装到另一个 Agent

### TRAE（本机）
1. 将整个 `ai-super-tutor` 文件夹复制到你的 TRAE 技能数据目录（一般为 `<数据目录>\.trae-cn\skills\`）下。
2. 在 `skill-config.json` 的 `managedSkills` 登记 `"ai-super-tutor": "user_upload"`。
3. 新开会话即可通过触发词启用。

### 其他支持 SKILL.md 的 Agent（Claude Code / Cursor / Codex CLI 等）
- 把 `SKILL.md`（连同文件夹名 `ai-super-tutor`）复制到该 Agent 约定的技能目录：
  - Claude Code：`.claude/skills/ai-super-tutor/`
  - Cursor：`.cursor/skills/ai-super-tutor/`
  - 其他：见各产品文档的 skills 约定。
- 纯提示词技能通常无需额外配置。

### 重新打包分发
```powershell
Compress-Archive -Path "skills\ai-super-tutor\*" -DestinationPath "ai-super-tutor.zip" -Force
```

## 3 种模式速查

| 模式 | 触发关键词 | AI 角色 | 适合 | 心法 |
|---|---|---|---|---|
| **A 费曼逆向教学** | 讲给你听 / 费曼 / 听我解释 | 跨界好奇外行 | 抽象概念、深层原理、直觉建立 | 讲不清楚 = 没真懂 |
| **B 苏格拉底考官** | 口试我 / 考我 / 苏格拉底 | 循循善诱阶梯考官（一次一问） | 逻辑因果、原理推演、思维脚手架 | 知识由你推导出来 |
| **C 布鲁姆通关** | 通关 / 关卡 / 验收这章 | 严谨关卡守门人（5题≥80% 放行） | 章节考核、复习自测、阶段性验收 | 地基不稳绝不放行 |

## 使用方法

1. **建立事实标尺**：粘贴讲义、给出文件路径，或直接让 AI 提炼知识点大纲并确认。
2. **选模式**：直接说想用的方式，或由 AI 引导选择。
3. **开始学习**：AI 按对应模式流程深度交互（你可随时说「进入费曼 / 换苏格拉底 / 开始通关」无缝切换，学习进度不丢失）。
4. **沉淀复习**：查看自动生成的 `learning-notes.md`，按艾宾浩斯排期进行周期复习。