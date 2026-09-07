# AI 超级私教（ai-super-tutor）· 可移植技能包

一份自包含、可分发、能安装进任意支持 `SKILL.md` 规范的 Agent（TRAE / Claude Code / Cursor 等）的通用学习辅导技能。

## 包内容

| 文件 | 作用 |
|---|---|
| `SKILL.md` | 技能本体（唯一必需文件），纯提示词驱动，无外部依赖 |
| `LICENSE.txt` | MIT 开源授权 |
| `manifest.json` | 包清单：名称/版本/安装步骤 |
| `README.md` | 本说明 |

## 为什么通用、可移植

- **零依赖**：不调用任何第三方工具，任何 Agent 都能运行。
- **自动降级**：优先用 `AskUserQuestion` 交互；环境没有该工具时自动退回纯文本提问，行为不变。
- **无本机路径**：不绑定任何目录、密钥或文档——讲义由用户随时注入。
- **语言中立**：默认与用户当前语言一致（中/英等均可）。

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
Compress-Archive -Path "skills\ai-super-tutor\*" -DestinationPath "ai-super-tutor.zip"
```

## 5 种模式速查

| 模式 | 触发关键词 | AI 角色 | 适合 | 心法 |
|---|---|---|---|---|
| A 费曼逆向教学 | 讲给你听 / 费曼 | 好奇小白学生 | 概念、英语、抽象机制 | 讲不清楚=没真懂 |
| B 苏格拉底考官 | 口试我 / 考我 / 苏格拉底 | 严厉考官（一次一问） | 核心原理、算法边界 | 绝不直接给答案 |
| C 布鲁姆通关 | 通关 / 关卡 / 守门人 | 冷酷守门人（≥80% 放行） | 语言基础、前后依赖课 | 地基不稳不看下一章 |
| D 魔鬼代言 | 挑刺 / 极端场景 | 挑剔资深架构师 | 软件工程、系统设计 | 极端场景下验韧性 |
| E TDD 对练 | 先用例 / 别给实现 | 测试用例出题官 | 函数、算法实操 | 先看用例再写实现 |

## 使用方法

1. **提供讲义（事实标尺）**：粘贴文本、给文件路径、或在工作区放大纲文档。
2. **选模式**：直接说想用的方式，或让 AI 询问。
3. **开始学习**：AI 按对应模式流程交互（你可随时说「进入费曼 / 换苏格拉底 / 开始通关」切换，进度不丢）。

> 注意：本技能是**学习辅导**，不用于拷问用户的项目/方案（那属于 `grilling`）。