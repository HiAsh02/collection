# AI Agent Skills & Plugins Collection

个人精选的 AI Agent Skills 与 Plugins 聚合导航仓库，采用**“三层软连接”**设计——既能像文件软连接一样直接从 GitHub 目录跳转至各上游仓库源码，又避免把外部代码全量拷贝进来造成仓库臃肿或版本漂移。

## 三层“软连接”架构

1. **Git 目录级软连接（`.gitmodules` + `160000` gitlink）**  
   5 个分类目录下的每个子文件夹都是标准的 Git Submodule 指针，GitHub 网页端直接渲染为可点击跳转的 `folder @ commit-sha`，不占本仓库源码体积，可用 `git submodule update --remote` 一键追新。
2. **文档导航级软连接（分类 `README.md` + 深链索引）**  
   每个分类目录配备独立导览文档，拆解上游仓库的子路径（例如 `poteto/plugins` 下的 `pstack`）、全部子 Skill 名称与适用场景。
3. **工具注册表级软连接（[`catalog.json`](./catalog.json) + [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json)）**  
   提供结构化的上游 `repo` / `ref` / `path` 指针，方便 Claude Code Marketplace、Magpie、`npx skills` 或自定义同步脚本直接读取安装。

---

## 目录结构

```text
collection/
├── .claude-plugin/
│   └── marketplace.json                  # Claude Code Marketplace 上游仓库索引
├── .gitmodules                           # 12 个上游仓库的 Git Submodule 软连接声明
├── catalog.json                          # 全量结构化索引（含兼容 Magpie / npx 的源描述）
├── 01-engineering-workflows/             # 01 · 软件工程工作流
│   ├── README.md
│   ├── dev-workflow        -> HiAsh02/dev-workflow
│   ├── superpowers         -> obra/superpowers
│   ├── mattpocock-skills   -> mattpocock/skills
│   └── poteto-plugins      -> poteto/plugins (重点子路径: pstack)
├── 02-architecture-and-memory/           # 02 · 架构理解、记忆与多 Agent 编排
│   ├── README.md
│   ├── poteto-how          -> poteto/how
│   ├── poteto-brainmaxxing -> poteto/brainmaxxing
│   └── poteto-noodle       -> poteto/noodle
├── 03-writing-and-content/               # 03 · 写作与文本去噪
│   ├── README.md
│   └── human-writing       -> KKKKhazix/human-writing
├── 04-visual-and-ip/                     # 04 · 视觉设计、封面与个人 IP
│   ├── README.md
│   ├── punk-posters        -> adrianpunk/Punk-Posters (原 Punk-Skill)
│   ├── punk-ip             -> adrianpunk/Punk-IP
│   └── punk-xhs            -> adrianpunk/Punk-xhs
├── 05-knowledge-and-media/               # 05 · 知识检索与播客媒体
│   ├── README.md
│   └── next-token-skill    -> next-token-tv/next-token-skill
└── 06-prompts-and-thinking/              # 06 · 提问、学习、决策与自我探索提示词
    └── README.md
```

---

## 分类速查总表

### [01 · 软件工程工作流（Engineering Workflows）](./01-engineering-workflows/README.md)

| 名称 | 软连接目录 | 上游仓库 | 核心 Skill / 亮点 | 适用场景 |
|---|---|---|---|---|
| **dev-workflow** | [`dev-workflow`](https://github.com/HiAsh02/dev-workflow/tree/70e5be60dccfb8ffa0343b1cb5d3d5f6ef62d988) | [`HiAsh02/dev-workflow`](https://github.com/HiAsh02/dev-workflow) | `dw-start` / `dw-design` / `dw-plan` / `dw-build` / `dw-debug` / `dw-review` / `dw-ship` / `dw-handoff` | 自研全流程工程规范：三档强度、风险升级、显式提交关口与双语支持 |
| **Superpowers** | [`superpowers`](https://github.com/obra/superpowers/tree/22f0b463e7a5e579904dd6211a520321035526f7) | [`obra/superpowers`](https://github.com/obra/superpowers) | 15 个 Skill：`using-superpowers`、`brainstorming`、`writing-plans`、`test-driven-development`、`systematic-debugging`、`subagent-driven-development` 等 | 高纪律性研发闭环、Red-Green-Refactor TDD 与子 Agent 执行 |
| **Matt Pocock Skills** | [`mattpocock-skills`](https://github.com/mattpocock/skills/tree/5863806dd4e15c63174bee4e7515a4256792ecfa) | [`mattpocock/skills`](https://github.com/mattpocock/skills) | `ask-matt`、`grill-me` / `grill-with-docs`、`to-spec`、`to-tickets`、`implement`、`tdd`、`code-review`、`teach` 等 | 先“拷问”对齐设计再写 Spec/Tickets，兼顾实用协作与学习辅助 |
| **Poteto Plugins (`pstack`)** | [`poteto-plugins`](https://github.com/poteto/plugins/tree/74dd2291e8e37b12fd6dc49b2acbd655c6bdaf12) | [`poteto/plugins`](https://github.com/poteto/plugins)（子目录 [`pstack`](https://github.com/poteto/plugins/tree/main/pstack)） | `poteto-mode`、`setup-pstack`、`automate-me`、`unslop`、21 条 `principle-*` 工程原则等共 35 个 Skill | 拒绝 AI Slop 代码，追求高信噪比、多模型协作与极简高质量交付 |

### [02 · 架构理解、记忆与多 Agent 编排（Architecture, Memory & Orchestration）](./02-architecture-and-memory/README.md)

| 名称 | 软连接目录 | 上游仓库 | 核心 Skill / 亮点 | 适用场景 |
|---|---|---|---|---|
| **How** | [`poteto-how`](https://github.com/poteto/how/tree/b1ef42969ea7a2bb50aa26c2480274828a0385e7) | [`poteto/how`](https://github.com/poteto/how) | `/how`（Explain 与多模型 Critique 双模式） | 接手陌生子系统时的资深工程师级架构梳理与问题审视 |
| **Brainmaxxing** | [`poteto-brainmaxxing`](https://github.com/poteto/brainmaxxing/tree/ec4d8e43dee639d6f5d94aed3ca16af7b298ecfc) | [`poteto/brainmaxxing`](https://github.com/poteto/brainmaxxing) | `brain`、`reflect`、`ruminate`、`meditate`、`plan`、`review`（配套 Obsidian Markdown Vault） | 会话复盘、挖掘历史对话经验并让 Agent 规则持续自我进化 |
| **Noodle** | [`poteto-noodle`](https://github.com/poteto/noodle/tree/82d2921c52370f23f29086de81ccfb600939c037) | [`poteto/noodle`](https://github.com/poteto/noodle) | Go 编排运行时 + `.agents/skills/` 下 29 个内置 Skill（含 `noodle`、`schedule`、`worktree`、`ast-grep` 等） | 基于 Skill 调度多 Agent 并行工作流与 Worktree 管理 |

### [03 · 写作与文本去噪（Writing & Content）](./03-writing-and-content/README.md)

| 名称 | 软连接目录 | 上游仓库 | 核心 Skill / 亮点 | 适用场景 |
|---|---|---|---|---|
| **Human Writing** | [`human-writing`](https://github.com/KKKKhazix/human-writing/tree/288297b6c2d9b6df23e0ceb64888443f15cfbcc3) | [`KKKKhazix/human-writing`](https://github.com/KKKKhazix/human-writing) | `human-writing`（v1.2.0 活人感写作） | 中文长文创作、改稿与去 AI 味（先审材料再动笔，拒绝模型腔与空话） |

### [04 · 视觉设计、封面与个人 IP（Visual & Personal IP）](./04-visual-and-ip/README.md)

| 名称 | 软连接目录 | 上游仓库 | 核心 Skill / 亮点 | 适用场景 |
|---|---|---|---|---|
| **Punk Posters / Skill** | [`punk-posters`](https://github.com/adrianpunk/Punk-Posters/tree/15b816cea5dcc7a3b028561d34604246369939b0) | [`adrianpunk/Punk-Posters`](https://github.com/adrianpunk/Punk-Posters)（原 `Punk-Skill`） | `punk-cover`、`punk-avatar`、`punk-ip-video-cover` | 小红书 / 公众号 / X / YouTube 封面、风格化头像与真人 IP 视频封面（个人非商用免费） |
| **Punk IP** | [`punk-ip`](https://github.com/adrianpunk/Punk-IP/tree/c5cbd8241cc92cd8583e878617c3788682e89a88) | [`adrianpunk/Punk-IP`](https://github.com/adrianpunk/Punk-IP) | `punk-ip-article-illustrations` | 从照片创建持久化个人 IP 角色，为长文生成画风一致的正文小剧场配图 |
| **Punk XHS Cards** | [`punk-xhs`](https://github.com/adrianpunk/Punk-xhs/tree/03a9c3d32e9d0d14a60ecb3999335e6b80fa16ea) | [`adrianpunk/Punk-xhs`](https://github.com/adrianpunk/Punk-xhs) | `punk-xhs-cards` | 将 Markdown 长文与个人 IP 制作成小红书书封与编号知识内页卡片 |

### [05 · 知识检索与播客媒体（Knowledge & Media）](./05-knowledge-and-media/README.md)

| 名称 | 软连接目录 | 上游仓库 | 核心 Skill / 亮点 | 适用场景 |
|---|---|---|---|---|
| **Next Token Skill** | [`next-token-skill`](https://github.com/next-token-tv/next-token-skill/tree/9419b1e873d01eaf14ca4122c025b02281b690e4) | [`next-token-tv/next-token-skill`](https://github.com/next-token-tv/next-token-skill) | `next-token`（`scripts/nexttoken.py`） | 检索《Next Token｜词元之外》AI 播客逐字稿与博客，输出 B 站 / YouTube 时间戳直跳引用 |

### [06 · 提问、学习、决策与自我探索提示词（Prompts & Thinking Models）](./06-prompts-and-thinking/README.md)

| 模块 | 文档索引 | 包含提示词 | 适用场景 |
|---|---|---|---|
| **问清问题** | [一. 问清问题](./06-prompts-and-thinking/README.md#一-问清问题) | 苏格拉底式提问 | 厘清真实困惑、区分事实/解释/价值判断并定位关键问题 |
| **学习** | [二. 学习](./06-prompts-and-thinking/README.md#二-学习) | 双层解释法、反向拆解、横纵分析法、事实核查 | 跨层次理解概念、拆解优秀成品、深度行研与联网事实核查 |
| **解决问题** | [三. 解决问题](./06-prompts-and-thinking/README.md#三-解决问题) | 专家会诊、第一性原理、跨领域借解 | 多视角会诊、剥离惯例重构方案、跨学科迁移机制 |
| **决策** | [四. 决策](./06-prompts-and-thinking/README.md#四-决策) | 双向钢人论证、用最小实验替代空想 | 对等论证两难抉择、设计低成本可逆最小实验验证假设 |
| **认识你自己** | [五. 认识你自己](./06-prompts-and-thinking/README.md#五-认识你自己) | 挖掘隐藏天赋、人生设计术 | 通过苏格拉底式追问生成个人天赋使用说明书与人生设计蓝图 |

---

## 常用维护与安装方式

### 1. 拉取本仓库与更新上游软连接

```bash
# 仅拉取索引与导航文档（不下载外部仓库体积）
git clone https://github.com/HiAsh02/collection.git

# 按需初始化全部或指定分类的子模块源码
git submodule update --init --recursive
git submodule update --init 04-visual-and-ip/punk-posters

# 将所有子模块软连接追新到各自上游 main 分支最新提交
git submodule update --remote
```

### 2. 按需安装到各 Agent 宿主

- **通用 Skill 安装器（Claude Code / Codex / Cursor / Antigravity 等）**：
  ```bash
  npx skills add obra/superpowers
  npx skills add mattpocock/skills
  npx skills add KKKKhazix/human-writing
  npx skills add adrianpunk/Punk-Posters
  npx skills add next-token-tv/next-token-skill
  ```
- **Claude Code Plugin Marketplace**：
  ```text
  /plugin marketplace add HiAsh02/collection
  ```
  > 注：本仓库根目录提供 [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json) 聚合索引；实际子路径插件（如 `poteto/plugins` 下的 `pstack`）或私有仓库（如 `HiAsh02/dev-workflow`）也可按各分类文档中的说明单独安装。
- **Cursor 插件（`pstack` / `how`）**：
  ```text
  /add-plugin pstack
  ```
- **`dev-workflow`（自研事务安装器）**：克隆 `HiAsh02/dev-workflow` 后运行 `node bin/dev-workflow.mjs install --host <codex|pi|grok-build|antigravity> --language <zh-CN|en> --target <project>`。
