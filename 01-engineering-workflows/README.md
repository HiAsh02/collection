# 01 · 软件工程工作流（Engineering Workflows）

本目录聚合 4 套面向 AI Coding Agent 的结构化工程工作流，覆盖从需求澄清、技术方案设计、计划拆解、TDD 实现、系统化排错到双轴审查与安全交付的完整研发闭环。

## 套件对比与选型

| 目录软连接 | 上游仓库 | 定位与特点 | 核心入口 Skill |
|---|---|---|---|
| [dev-workflow](./dev-workflow) | [`HiAsh02/dev-workflow`](https://github.com/HiAsh02/dev-workflow) | 自研：证据驱动、三档强度（`quick`/`standard`/`rigorous`）、显式提交/远端授权关口、支持 `en`/`zh-CN` 与多宿主事务安装 | `dw-start` |
| [superpowers](./superpowers) | [`obra/superpowers`](https://github.com/obra/superpowers) | 纪律驱动的经典 Agent 工程框架：强调苏格拉底式需求发散、Red-Green-Refactor TDD 与子 Agent 驱动执行 | `using-superpowers` |
| [mattpocock-skills](./mattpocock-skills) | [`mattpocock/skills`](https://github.com/mattpocock/skills) | 实用派研发流水线：主打“苏格拉底拷问（Grill）→ Spec → Tickets → 实现 → 审查”，附带个人学习与协作 Skill | `ask-matt` |
| [poteto-plugins](./poteto-plugins) | [`poteto/plugins`](https://github.com/poteto/plugins) | Cursor 插件合集，核心子路径 [`pstack`](https://github.com/poteto/plugins/tree/main/pstack) 主打“降噪写少而精的代码”、多模型协同与 21 条显式工程原则 | `poteto-mode` |

---

## 各套件核心 Skill 清单

### 1. `dev-workflow`（自研 `dw-*` 系列，8 个核心 Skill）

- `dw-start`：统一入口路由器，识别意图并匹配 7 个内部 Playbook、流程强度与风险等级
- `dw-design`：澄清需求、比选架构、整理术语与 ADR，高影响变更前锁定设计批准
- `dw-plan`：输出 `spec.md`、垂直切片、无环依赖（`blocked_by`）、验证命令与回滚方案
- `dw-build`：保护脏工作区，按切片执行 TDD/验证并支持单 Agent 降级
- `dw-debug`：复现缺陷、缩小范围、提出可证伪假设并实施授权修复
- `dw-review`：基于源码 Diff 与重跑证据进行 `Spec` + `Standards` 双轴审查
- `dw-ship`：区分 `LOCAL_COMMIT`、`REMOTE_WRITE`、`DESTRUCTIVE` 三级授权关口
- `dw-handoff`：结合磁盘账本（`run-state.json`、`worklog.md`）与 Git 状态跨会话恢复

### 2. `superpowers`（15 个 Skill）

- **入口与元技能**：`using-superpowers`、`writing-skills`、`diagnosing-superpowers`
- **设计与规划**：`brainstorming`、`writing-plans`
- **执行与并行**：`executing-plans`、`subagent-driven-development`、`dispatching-parallel-agents`、`using-git-worktrees`
- **质量与验证**：`test-driven-development`、`systematic-debugging`、`verification-before-completion`
- **审查与收尾**：`requesting-code-review`、`receiving-code-review`、`finishing-a-development-branch`

### 3. `mattpocock/skills`（`skills/` 目录下分 4 个子目录）

- **`engineering`（20 项）**：`ask-matt`、`setup-matt-pocock-skills`、`grill-with-docs`、`to-spec`、`to-tickets`、`implement`、`implement-spec`、`tdd`、`code-review`、`diagnosing-bugs`、`domain-modeling`、`codebase-design`、`improve-codebase-architecture`、`pr`、`prototype`、`research`、`retro`、`triage`、`wayfinder`、`wizard`
- **`productivity`（7 项）**：`grill-me`、`grilling`、`handoff`、`teach`、`to-questionnaire`、`wait-what`、`writing-for-agents`
- **`misc`（4 项）**：`git-guardrails-claude-code`、`migrate-to-shoehorn`、`scaffold-exercises`、`setup-pre-commit`
- **`in-progress`（8 项）**：`chief-of-staff`、`claude-handoff`、`loop-me`、`setup-ts-deep-modules`、`software-factory`、`writing-beats`、`writing-fragments`、`writing-shape`

### 4. `poteto/plugins`（重点子路径：[`pstack`](https://github.com/poteto/plugins/tree/main/pstack)）

该仓库是 Cursor 官方插件规范与插件集（含 `pstack`、`orchestrate`、`thermos`、`cursor-team-kit`、`continual-learning`、`ralph-loop` 等）。其中 **`pstack/skills/`（35 个 Skill）** 包含：

- **调度与核心工作流（14 项）**：`poteto-mode`、`setup-pstack`、`automate-me`、`architect`、`arena`、`figure-it-out`、`how`、`interrogate`、`reflect`、`show-me-your-work`、`tdd`、`typescript-best-practices`、`unslop`、`why`
- **工程原则技能（21 项 `principle-*`）**：`principle-boundary-discipline`、`principle-build-the-lever`、`principle-encode-lessons-in-structure`、`principle-exhaust-the-design-space`、`principle-experience-first`、`principle-fix-root-causes`、`principle-foundational-thinking`、`principle-guard-the-context-window`、`principle-laziness-protocol`、`principle-make-operations-idempotent`、`principle-migrate-callers-then-delete-legacy-apis`、`principle-minimize-reader-load`、`principle-model-the-domain`、`principle-never-block-on-the-human`、`principle-outcome-oriented-execution`、`principle-prove-it-works`、`principle-redesign-from-first-principles`、`principle-separate-before-serializing-shared-state`、`principle-sequence-verifiable-units`、`principle-subtract-before-you-add`、`principle-type-system-discipline`
