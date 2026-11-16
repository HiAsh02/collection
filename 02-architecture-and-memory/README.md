# 02 · 架构理解、记忆与多 Agent 编排（Architecture, Memory & Orchestration）

本目录聚焦代码库深层理解、Agent 持久化记忆沉淀以及多 Skill 自动化调度运行，主要收录 `poteto` 开源的三套代表性基础设施。

## 套件总览

| 目录软连接 | 上游仓库 | 定位与核心能力 | Skill 路径 |
|---|---|---|---|
| [poteto-how](https://github.com/poteto/how/tree/b1ef42969ea7a2bb50aa26c2480274828a0385e7) | [`poteto/how`](https://github.com/poteto/how) | 代码库架构讲解：按高级工程师 Onboarding 水准拆解子系统与调用链，支持并行探索与多模型 Critique | `skills/how` |
| [poteto-brainmaxxing](https://github.com/poteto/brainmaxxing/tree/ec4d8e43dee639d6f5d94aed3ca16af7b298ecfc) | [`poteto/brainmaxxing`](https://github.com/poteto/brainmaxxing) | 基于 Markdown / Obsidian Vault 的极简持久化记忆与自我进化闭环 | `.agents/skills/*` |
| [poteto-noodle](https://github.com/poteto/noodle/tree/82d2921c52370f23f29086de81ccfb600939c037) | [`poteto/noodle`](https://github.com/poteto/noodle) | 基于 Go 构建的 Skill 驱动多 Agent 编排运行时，内置任务调度、Worktree 隔离与 29 个工程 Skill | `.agents/skills/*` |

---

## 详细拆解

### 1. `poteto/how`（1 个核心 Skill）

- **`how`**：提供两种自动切换模式：
  - **Explain（默认）**：输出包含 Overview、Key Concepts、How It Works、Where Things Live、Gotchas 的结构化架构解读；复杂问题会拆分为 2–4 个并行探索子 Agent 再汇总。
  - **Critique**：先完成架构解读，再调度多个不同模型视角的 Critic 暴露设计与架构隐患。

### 2. `poteto/brainmaxxing`（6 个 Skill + 16 条初始工程原则）

围绕 `brain/`（兼容 Obsidian 的 Markdown 知识库）形成“记录 → 提炼 → 修剪 → 复用”闭环：

- **学习闭环**：`reflect`（会话后沉淀经验）、`ruminate`（从历史会话挖掘隐含知识）、`meditate`（定期审计、合并并精简冗余规则）、`brain`（知识库索引与维护）
- **工程辅助**：`plan`（结合原则做分阶段规划）、`review`（基于原则的方案与代码审查）

### 3. `poteto/noodle`（`.agents/skills/` 下 29 个内置 Skill）

- **编排与元技能**：`noodle`、`schedule`、`worktree`、`find-skills`、`skill-creator`、`codex`、`todo`
- **研发执行链**：`plan`、`execute`、`debugging`、`testing`、`commit`、`oops`、`refine`、`quality`、`review`、`adversarial-review`、`unslop`
- **记忆循环**：`brain`、`reflect`、`ruminate`、`meditate`
- **专项栈与前端设计**：`ast-grep`、`go-best-practices`、`ts-best-practices`、`react-best-practices`、`frontend-design`、`interaction-design`、`make-interfaces-feel-better`
