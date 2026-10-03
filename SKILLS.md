# 本机 Agent 技能清单（Skills Inventory）

> 扫描时间：2026-10-03 17:39 ｜ 机器：Windows（用户 denghao）｜ 扫描工具：DSH 技能管理 v1.1.8 数据核对
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
| brainstorming | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 创作前先澄清意图与需求：任何新功能/新组件动手前必须先头脑风暴 | 一致 |
| diagnosing-superpowers | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | superpowers 会话出问题时复盘原因并生成 bug 报告 | 一致 |
| dispatching-parallel-agents | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 两个以上互不依赖的任务并行派发子代理处理 | 一致 |
| executing-plans | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 按既定实现计划在当前会话逐任务执行（实施者视角） | 一致 |
| find-skills | 4 | ✅ | 🔗 | 🔗 |  | ✅ | 帮用户发现并安装可用技能（“有没有技能能做 X？”） | 一致 |
| finishing-a-development-branch | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 开发分支收尾：决定合并、PR 还是清理 | 一致 |
| receiving-code-review | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 收到审查意见先技术求证再改，不盲从不敷衍 | 一致 |
| requesting-code-review | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 完成任务或合并前发起代码审查，核验是否满足需求 | 一致 |
| subagent-driven-development | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 用子代理逐任务执行实现计划，适合任务相互独立时 | 一致 |
| systematic-debugging | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 遇到 bug/测试失败先系统化定位根因，再谈修复 | 一致 |
| test-driven-development | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 测试驱动开发：先写测试再写实现，红-绿-重构 | 一致 |
| using-git-worktrees | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 用 git worktree 隔离功能开发，不污染当前工作区 | 一致 |
| using-superpowers | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 会话开始时建立“先查技能再回复”的使用约定 | 一致 |
| verification-before-completion | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 宣称“完成/修好/通过”前必须先跑验证命令，凭证据说话 | 一致 |
| writing-plans | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 把需求写成可执行的实现计划，动代码之前用 | 一致 |
| writing-skills | 5 | ✅ | 🔗 | 🔗 | 🔗 | ✅ | 创建/修改技能（SKILL.md）的规范流程与部署前校验 | 一致 |

## 前端与设计 ｜ 7 个

| 技能 | 安装 | 公共 | Claude | Trae | CodeBuddy | WorkBuddy | 简介 | 版本 |
|---|---|---|---|---|---|---|---|---|
| ardot-pixel-restore | 1 |  |  |  |  | ✅ | Ardot 设计稿画板一比一像素级还原为 HTML 的 diff 闭环工作流 | — |
| frontend-design | 4 | ✅ | 🔗 | 🔗 |  | ✅ | 新建/重塑界面时的视觉方向指导，避免模板化外观 | 一致 |
| frontend-project-delivery | 2 | ✅ |  |  |  | ✅ | 前端需求/设计/契约跨会话漂移时的交付与继续开发 | 一致 |
| impeccable | 2 | ✅ |  |  |  | ✅ | 前端界面设计-审查-打磨全流程：落地页、仪表盘、组件、空状态等 | 一致 |
| mini-program-ui-showcase | 2 | ✅ |  |  |  | ✅ | 小程序 UI 展示图 + 小红书爆款文案生成（Puppeteer 截图） | 一致 |
| taste | 2 | ✅ |  |  |  | ✅ | 落地页、作品集与改版的反模板审美设计 | 一致 |
| ui-ux-pro-max | 3 | ✅ | 🔗 |  |  | ✅ | UI/UX 设计智能库：风格、配色、字体搭配、UX 规范、图表一键检索 | 一致 |

## 视频与内容创作 ｜ 5 个

| 技能 | 安装 | 公共 | Claude | Trae | CodeBuddy | WorkBuddy | 简介 | 版本 |
|---|---|---|---|---|---|---|---|---|
| gc-minimal-zine-poster-v0-1 | 2 | ✅ |  |  |  | ✅ | 极简 zine 风纸感海报提示词与配图生成，日韩编辑风留白 | 一致 |
| hyperframes | 2 | ✅ |  |  |  | ✅ | HTML 视频合成：标题卡、字幕、转场、TTS 配音、音频可视化 | 一致 |
| remotion-video-toolkit | 2 | ✅ |  |  |  | ✅ | Remotion + React 程序化视频全家桶：动画、字幕、图表、渲染、模板 | ⚠️ 2 个版本 |
| social-card-generator | 2 | ✅ |  |  |  | ✅ | 文案转社交媒体分享图（HTML + Puppeteer 截图） | 一致 |
| video-shotcraft | 2 | ✅ |  |  |  | ✅ | 镜头配方卡 + 已验收模板制作电影感产品视频，运镜与节奏卡点 | 一致 |

## 平台与效率工具 ｜ 8 个

| 技能 | 安装 | 公共 | Claude | Trae | CodeBuddy | WorkBuddy | 简介 | 版本 |
|---|---|---|---|---|---|---|---|---|
| anysearch | 2 | ✅ |  |  |  | ✅ | 实时搜索引擎：网页/垂直域/并行批量搜索与网页内容提取 | 一致 |
| cc | 2 | ✅ | ✅ |  |  |  | 用 Claude Code 干活的规范：headless 调用 + worktree 隔离 + DSH 验收 | 一致 |
| obsidian | 2 | ✅ |  |  |  | ✅ | 操作 Obsidian 笔记库（纯 Markdown），配合 notesmd-cli 自动化 | 一致 |
| obsidian-daily-archive | 2 | ✅ |  |  |  | ✅ | 每日把 WorkBuddy 工作记忆日志归档进 Obsidian 知识库 | 一致 |
| tabbit | 2 | 🔗 | 🔗 |  |  |  | 通过 Tabbit CLI 做浏览器导航、交互与视觉验证 | 一致 |
| token-wise | 2 | ✅ |  |  |  | ✅ | 省 token 不降质：僵尸会话、上下文膨胀、冗长输出的分层优化 | 一致 |
| windows-rogue-app-uninstall | 2 | ✅ |  |  |  | ✅ | 卸载顽固/流氓软件：假卸载器、驻留服务、DLL 注入、死文件关联 | ⚠️ 2 个版本 |
| zhongzhuan-task | 3 | ✅ |  |  | ✅ | ✅ | 双角色跨平台协作：经 Obsidian 中转层制定、领取、执行、回报任务 | ⚠️ 2 个版本 |

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

*本清单由扫描脚本自动生成。「简介」列为中文摘要，原始描述以各技能目录下的 `SKILL.md` 为准；`cc`、`taste`、`tabbit`、`anysearch` 等第三方技能版权归原作者所有，本仓库仅作索引，不包含技能本体文件。*
