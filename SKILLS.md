# 本机 Agent 技能清单（Skills Inventory）

> 扫描时间：2026-10-03 17:30 ｜ 机器：Windows（用户 denghao）｜ 扫描工具：DSH 技能管理 v1.1.8 数据核对
>
> **去重规则**：同一技能（按技能目录名/`SKILL.md` 中的 `name` 识别）在本机多个 Agent 中安装时，清单只收录一条，并在「来源」矩阵中标注每个 Agent 的安装方式：✅ = 实体副本，🔗 = 目录链接（junction/symlink），空白 = 未安装。

## 总览

| 指标 | 数值 |
|---|---|
| DSH 技能页计数（去链接前） | **71** |
| 去重后独立技能 | **36** |
| 技能目录总数（含链接，不含 Codex `.system`） | 122 |
| 实体副本 / 目录链接 | 70 / 52 |
| 多版本分叉技能 | 3 个 |

### 各技能源映射

| 来源 | 本机路径 | 技能目录数 | 去重后计入 | 说明 |
|---|---|---|---|---|
| 公共Agent | `~/.agents/skills` | 35 | 35 | 本机公共技能主库（其他 Agent 多以链接复用） |
| Claude | `~/.claude/skills` | 20 | 1 | 19/20 为指向公共库的链接，仅 `cc` 是独立副本 |
| Trae国内版 | `~/.trae-cn/skills` | 17 | 0 | 17 个全部为指向公共库的链接 |
| CodeBuddy | `~/.codebuddy/skills` | 16 | 1 | 15/16 为链接，仅 `zhongzhuan-task` 是独立副本（旧版本） |
| WorkBuddy | `~/.workbuddy/skills` | 34 | 34 | 全部为实体副本，含独有技能 `ardot-pixel-restore` |
| Codex | `~/.codex/skills` | 1 | 0 | 仅 `.system` 内置技能目录（无 SKILL.md，不计入） |

> 另有 Claude 侧 1 个、CodeBuddy 侧 1 个实体副本与公共库内容完全一致/部分分叉，详见[版本分叉](#版本分叉)。

## 开发工作流（superpowers 系列） ｜ 16 个

| 技能 | 安装 | 公共 | Claude | Trae | CodeBuddy | WorkBuddy | 简介 | 版本 |
|---|---|---|---|---|---|---|---|---|
| brainstorming | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | You MUST use this before any creative work - creating features, buildi… | 一致 |
| diagnosing-superpowers | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when a superpowers session went wrong and your human partner wants… | 一致 |
| dispatching-parallel-agents | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when facing 2+ independent tasks that can be worked on without sha… | 一致 |
| executing-plans | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when executing an implementation plan in the current session as th… | 一致 |
| find-skills | 4 | ✅ | 🔗 | 🔗 |  | ✅ | Helps users discover and install agent skills when they ask questions … | 一致 |
| finishing-a-development-branch | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when implementation is complete, all tests pass, and you need to d… | 一致 |
| receiving-code-review | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when receiving code review feedback, before implementing suggestio… | 一致 |
| requesting-code-review | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when completing tasks, implementing major features, or before merg… | 一致 |
| subagent-driven-development | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when executing implementation plans with independent tasks in the … | 一致 |
| systematic-debugging | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when encountering any bug, test failure, or unexpected behavior, b… | 一致 |
| test-driven-development | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when implementing any feature or bugfix, before writing implementa… | 一致 |
| using-git-worktrees | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when starting feature work that needs isolation from current works… | 一致 |
| using-superpowers | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when starting any conversation - establishes how to find and use s… | 一致 |
| verification-before-completion | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when about to claim work is complete, fixed, or passing, before co… | 一致 |
| writing-plans | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when you have a spec or requirements for a multi-step task, before… | 一致 |
| writing-skills | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | Use when creating new skills, editing existing skills, or verifying sk… | 一致 |

## 前端与设计 ｜ 7 个

| 技能 | 安装 | 公共 | Claude | Trae | CodeBuddy | WorkBuddy | 简介 | 版本 |
|---|---|---|---|---|---|---|---|---|
| ardot-pixel-restore | 1 |  |  |  |  | ✅ | 将 Ardot（或任意）设计稿画板一比一还原为 HTML 的像素 diff 闭环工作流。当用户给出设计稿截图/画板导出图并要求"还原/复刻/… | — |
| frontend-design | 4 | ✅ | 🔗 | 🔗 |  | ✅ | Guidance for distinctive, intentional visual design when building new … | 一致 |
| frontend-project-delivery | 2 | ✅ |  |  |  | ✅ | Use when delivering or continuing frontend features whose requirements… | 一致 |
| impeccable | 2 | ✅ |  |  |  | ✅ | Use when the user wants to design, redesign, shape, critique, audit, p… | 一致 |
| mini-program-ui-showcase | 2 | ✅ |  |  |  | ✅ | — | 一致 |
| taste | 2 | ✅ |  |  |  | ✅ | Anti-slop frontend skill for landing pages, portfolios, and redesigns.… | 一致 |
| ui-ux-pro-max | 3 | ✅ | 🔗 |  |  | ✅ | UI/UX design intelligence for web and mobile. Searchable local databas… | 一致 |

## 视频与内容创作 ｜ 5 个

| 技能 | 安装 | 公共 | Claude | Trae | CodeBuddy | WorkBuddy | 简介 | 版本 |
|---|---|---|---|---|---|---|---|---|
| gc-minimal-zine-poster-v0-1 | 2 | ✅ |  |  |  | ✅ | Generate Minimal Zine Poster v0.1 poetic paper-poster prompts and the … | 一致 |
| hyperframes | 2 | ✅ |  |  |  | ✅ | Create video compositions, animations, title cards, overlays, captions… | 一致 |
| remotion-video-toolkit | 2 | ✅ |  |  |  | ✅ | Complete toolkit for programmatic video creation with Remotion + React… | ⚠️ 2 个版本 |
| social-card-generator | 2 | ✅ |  |  |  | ✅ | Generate shareable social media image cards from text/marketing copy u… | 一致 |
| video-shotcraft | 2 | ✅ |  |  |  | ✅ | Create cinematic product videos from shot recipe cards, a validated te… | 一致 |

## 平台与效率工具 ｜ 8 个

| 技能 | 安装 | 公共 | Claude | Trae | CodeBuddy | WorkBuddy | 简介 | 版本 |
|---|---|---|---|---|---|---|---|---|
| anysearch | 2 | ✅ |  |  |  | ✅ | Real-time search engine supporting web search, vertical domain search,… | 一致 |
| cc | 2 | ✅ | ✅ |  |  |  | 当用户要求用 Claude Code（cc）完成/实现/修改项目代码，或需要一个独立编码执行者而由 DSH 负责规划与审查时使用。规范：he… | 一致 |
| obsidian | 2 | ✅ |  |  |  | ✅ | Work with Obsidian vaults (plain Markdown notes) and automate via note… | 一致 |
| obsidian-daily-archive | 2 | ✅ |  |  |  | ✅ | 每日自动将 WorkBuddy 工作记忆日志归档到 Obsidian 知识库。扫描 .workbuddy/memory/YYYY-MM-DD… | 一致 |
| tabbit | 2 | 🔗 | 🔗 |  |  |  | Use for browser navigation, inspection, interaction, and visual verifi… | 一致 |
| token-wise | 2 | ✅ |  |  |  | ✅ | Save AI model tokens and cost without degrading quality. Use when the … | 一致 |
| windows-rogue-app-uninstall | 2 | ✅ |  |  |  | ✅ | Remove stubborn/rogue Windows software (毒瘤软件) that survives normal uni… | ⚠️ 2 个版本 |
| zhongzhuan-task | 3 | ✅ |  |  | ✅ | ✅ | 双角色跨平台 agent 协作协议：通过 Obsidian 中转层（D:\文档\Agent-knowledge-base\中转层\）制定、领… | ⚠️ 2 个版本 |

## 版本分叉

以下技能在不同 Agent 中存在内容不同的副本（按 `SKILL.md` 的 SHA-256 判定），建议择优合并后统一为链接：

| 技能 | 分叉情况 | 差异要点 | 建议 |
|---|---|---|---|
| `zhongzhuan-task` | 公共Agent/WorkBuddy 一致；CodeBuddy 为旧版 | CodeBuddy 版中转层路径指向旧目录 `D:\文档\workSpace\中转层\`，新版为 `D:\文档\Agent-knowledge-base\中转层\` | 以公共版为准，将 CodeBuddy 副本替换为链接 |
| `remotion-video-toolkit` | 公共Agent 与 WorkBuddy 各一版 | WorkBuddy 的 SKILL.md 更新（2026-09-08，155 行）但目录只有 2 个文件；公共版文件齐全（35 个）但 SKILL.md 较旧（2026-08-25） | 将 WorkBuddy 新版 SKILL.md 合并回公共版 |
| `windows-rogue-app-uninstall` | 公共Agent 与 WorkBuddy 各一版 | WorkBuddy 版更新（2026-09-01，65 行 vs 60 行） | 以 WorkBuddy 版为准同步回公共版 |

## 诊断异常（DSH 提示 2 个）

| 技能 | 问题 | 修复建议 |
|---|---|---|
| `mini-program-ui-showcase` | frontmatter 缺少 `description` 字段（仅 `name` + `agent_created`） | 补充一行 `description:` 即可恢复正常 |
| `ardot-pixel-restore` | frontmatter 结束符 `---` 未独立成行（与 description 挤在同一行），解析失败 | 在 description 行后单独一行补 `---` |

## 附录：不计入 71 的内置技能

- **Codex 内置**（`~/.codex/skills/.system/`，6 个）：`imagegen`、`openai-docs`、`plugin-creator`、`review-agent`、`skill-creator`、`skill-installer`
- **Trae 国内版内置**（`~/.trae-cn/builtin_skills/`，4 个）：`TRAE-code-review`、`TRAE-debugger`、`TRAE-generate-mini-app`、`TRAE-security-review`

---

*本清单由扫描脚本自动生成；`cc`、`taste`、`tabbit`、`anysearch` 等第三方技能版权归原作者所有，本仓库仅作索引，不包含技能本体文件。*
