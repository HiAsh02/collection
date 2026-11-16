# 05 · 知识检索与播客媒体（Knowledge & Media）

本目录收录外部知识源、音视频逐字稿与播客观点溯源类的 Skill。

## 套件总览

| 目录软连接 | 上游仓库 | 定位与核心能力 | Skill 路径 |
|---|---|---|---|
| [next-token-skill](https://github.com/next-token-tv/next-token-skill/tree/9419b1e873d01eaf14ca4122c025b02281b690e4) | [`next-token-tv/next-token-skill`](https://github.com/next-token-tv/next-token-skill) | 《Next Token｜词元之外》中文 AI 播客逐字稿与博客检索工具 | `next-token/` |

---

## 核心特性：`next-token`

- **定位**：检索四位主理人（杨攀、歸藏、橘子、向阳乔木）在《Next Token｜词元之外》播客及衍生文章中的讨论内容。
- **实现机制**：通过 `scripts/nexttoken.py`（仅依赖 Python 3）自动同步并缓存线上节目逐字稿与博客文章到本地。
- **高频用法**：
  - `search`：多关键词检索原话与相关文章，并支持 `--speaker`、`--episode`、`--context` 过滤；
  - `brief` / `related` / `timeline`：按专题聚合、查看共现概念或按期追踪观点演进；
  - `episodes` / `read`：浏览全部节目章节或精读指定章节全文，回答中可直接附上 B 站 / YouTube 时间戳直跳链接。
