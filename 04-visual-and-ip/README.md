# 04 · 视觉设计、封面与个人 IP（Visual & Personal IP）

本目录收录 `adrianpunk` 开源的 Punk 系列视觉生成 Skill 套件，覆盖多平台封面设计、风格化头像、个人 IP 角色一致性插图以及小红书知识卡片制作。

> **开源与商用提示**：该系列仓库 `v2.0.0` 及后续版本源码公开、个人非商用免费；若用于企业、团队、商业内容、营销推广或收费服务等商业用途，须按各仓库 `COMMERCIAL-LICENSE.md` / `LICENSE-PERSONAL.md` 取得商业授权。

## 套件总览

| 目录软连接 | 上游仓库 | 定位与核心能力 | 包含 Skill |
|---|---|---|---|
| [punk-posters](./punk-posters) | [`adrianpunk/Punk-Posters`](https://github.com/adrianpunk/Punk-Posters)（原 `Punk-Skill`） | 多平台内容封面、风格化头像与个人 IP 视频封面生成 | `punk-cover`、`punk-avatar`、`punk-ip-video-cover` |
| [punk-ip](./punk-ip) | [`adrianpunk/Punk-IP`](https://github.com/adrianpunk/Punk-IP) | 个人 IP 角色设定持久化与一致画风的文章正文小剧场插图 | `punk-ip-article-illustrations` |
| [punk-xhs](./punk-xhs) | [`adrianpunk/Punk-xhs`](https://github.com/adrianpunk/Punk-xhs) | Markdown 教程/长文转小红书主题色封面 + 编号知识卡片 | `punk-xhs-cards` |

---

## 各 Skill 职责详情

### 1. `Punk-Posters`（`skills/` 下 3 个 Skill）

- **`punk-cover`**：将文章、笔记或推文草稿生成平台适配封面（小红书、微信公众号、X / Twitter、YouTube、Instagram、Medium 等），支持自动识别中英文模式与长宽比。
- **`punk-avatar`**：生成人物、宠物、物品的风格化头像，以及宠物纪念卡、超现实人物纸艺立体图。
- **`punk-ip-video-cover`**：从人物照片提取四色色板、抠出真人主体，并结合视频标题构图生成个人 IP 视频封面。

### 2. `Punk-IP`（根目录 `SKILL.md`）

- **`punk-ip-article-illustrations`**：从真人照片创建并持久化个人 IP 角色设定卡（支持 `retro-flat-3d` 复古彩色扁平 3D 与 `loose-watercolor` 松散线描水彩两种画风），后续读取文章或网页内容自动生成角色一致的正文配图与流程拆解图。

### 3. `Punk-xhs`（`punk-xhs-cards/`）

- **`punk-xhs-cards`**：按“人物确认 → 卡片样式确认 → 封面确认”三道确认门执行，将带代码/截图/流程图的 Markdown 长文转换为“主题色书封 + 16:9 macOS 窗口 IP 插图 + 编号知识内页”，同时附带小红书标题、正文与 Tags。
