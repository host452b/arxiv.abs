# arxiv.abs — 专题集格式规范 / Collection Format Standards

> 本文档是所有子专题集 README 的**权威格式标准**。新增专题或修改现有专题时，必须遵守以下规范。
>
> This document defines the **authoritative format standard** for all sub-collection READMEs. All new and existing collections must comply.

---

## 核心要求 / Core Requirements

### 1. 双语 README / Bilingual README

每个专题集**必须**同时维护两个 README 文件，内容并行：

- `README.md` — 英文版
- `README.zh-CN.md` — 中文版

两个文件底部互相链接，并链回主目录 `../README.md`。

---

### 2. 搜索主题表 / Search Topics Table

每个专题集必须列出所有搜索类别，格式如下：

```markdown
| # | 主题/Topic | 关键词/Keywords | 论文数/Papers | 结果文件/File |
|---|-----------|----------------|--------------|---------------|
| 01 | ... | keyword1 / keyword2 | 200 | [01-xxx.json](search-results/01-xxx.json) |
```

表格下方注明：**原始结果 N 篇 → 去重后 M 篇摘要**

---

### 3. ★ 80/20 二八定律最佳实践（核心要求）/ 80/20 Pareto Best Practices (Core Requirement)

**每个专题集的每个搜索类别或内容分段，都必须附上「二八定律核心最佳实践」总结。**

**Every search category or content segment in every collection must include an 80/20 Pareto best practices summary.**

#### 原则 / Principle

> 在该领域中，找出 **20% 的关键实践 / 技术 / 观点**，说明其如何覆盖 **80% 的效果 / 认可度 / 核心问题**。
>
> Identify the **20% of key practices / techniques / insights** that account for **80% of the outcomes / recognition / core problems** in that domain.

#### 标准格式 / Standard Format

````markdown
### XX 类别名称

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **核心实践 1**：简短说明 | 覆盖了什么效果，来自哪类证据 |
| **核心实践 2**：简短说明 | 覆盖了什么效果，来自哪类证据 |

> 一句话总结：这两条如何组合覆盖该类别 80% 的核心问题。
````

英文版对应格式：

````markdown
### XX Category Name

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Key Practice 1**: brief description | What outcome it covers, evidence basis |
| **Key Practice 2**: brief description | What outcome it covers, evidence basis |

> One-line summary: how these two together cover 80% of the core problems in this category.
````

#### 规则 / Rules

- 每个类别：**至少 1 条，通常 2 条**关键杠杆（过多则失去二八意义）
- 关键杠杆必须是**该类别论文中高频出现的共识**，不是主观推测
- 覆盖效果说明需要**具体**（如：减少 80% 的 cache miss、覆盖 80% 的视觉质量需求）
- 每个类别末尾加一句 `> 总结语`，说明两条合起来的覆盖范围

---

### 4. 按年份组织摘要 / Year-Based Abstract Organization

摘要文件统一按年份归档：

```
专题目录/
├── YYYY/
│   └── abstracts/
│       ├── ARXIVID.txt
│       └── ...
```

README 中按年份列出论文数与目录链接：

```markdown
| 年份/Year | 论文数/Papers | 目录/Directory |
|-----------|--------------|----------------|
| 2024 | 450 | [2024/abstracts/](2024/abstracts/) |
```

---

### 5. search-index.json

每个专题集根目录下必须有 `search-index.json`，记录所有搜索查询的元数据：

```json
[
  {
    "id": "01",
    "topic": "类别名称",
    "query": "keyword1 OR keyword2",
    "category": "cs",
    "sort": "relevance",
    "max": 200,
    "results": 200,
    "file": "search-results/01-xxx.json"
  }
]
```

---

### 6. 知识文档 / Knowledge Document

每个专题集应有一个独立的**深度知识文档**（非 README），存放：

- 核心发现 / 顾问分析 / 路线图 / 技术总结
- 详细数据引用（论文来源、arXiv ID、关键数据点）

| 专题 | 知识文档 | 说明 |
|------|---------|------|
| `arxiv.prompt` | `prompt_ai.md` / `.zh-CN.md` | 50 项核心技巧 |
| `arxiv.agi-scifi` | `agi-scifi.md` / `.zh-CN.md` | 核心发现总结 |
| `arxiv.agent-skills` | `agent-skills-findings.zh-CN.md` | 顾问框架分析 |
| `arxiv.ai-human-future` | `ai-future-findings.zh-CN.md` | 未来文明分析 |
| `arxiv.qbio-health` | `health-findings.zh-CN.md` | 健康干预分析 |
| `arxiv.game-dev` | `readme_game_roadmap.md` | 游戏开发全景路线图 |
| `arxiv.game-dev-with-ai` | `readme_game_dev_with_ai.md` | Human × AI 游戏开发全景与路线图 |

---

### 7. 导航页脚 / Navigation Footer

每个 README 底部必须有导航链接：

```markdown
[中文说明](README.zh-CN.md) | [知识文档](xxx.md) | [返回主目录](../README.md)
[English README](README.md) | [Knowledge Doc](xxx.md) | [Back to main](../README.md)
```

---

## 各专题 80/20 完成状态 / 80/20 Completion Status

| 专题 | 类别/分段数 | 80/20 已完成 |
|------|------------|-------------|
| `arxiv.game-dev` | 29 个类别 | ✅ 完成 |
| `arxiv.agent-skills` | 14 个技能类别 | ✅ 完成 |
| `arxiv.ai-human-future` | 12 个搜索主题 | ✅ 完成 |
| `arxiv.qbio-health` | 7 个主题 | ✅ 完成 |
| `arxiv.prompt` | 8 大章节 | ✅ 完成 |
| `arxiv.agi-scifi` | 10 大集群 | ✅ 完成 |
| `arxiv.game-dev-with-ai` | 25 个类别 | ✅ 完成 |
| `arxiv.software-engineering` | 35 个类别（8 大集群） | ✅ 完成 |
| `arxiv.qa-quality-engineering` | 35 个类别（7 大集群） | ✅ 完成 |
| `arxiv.agent-harness` | 42 个搜索（12 大集群） | ✅ 完成 |
| `arxiv.anthropic-claude` | 35 个搜索（12 大集群） | ✅ 完成 |

---

## 整体数据汇总 / Overall Statistics

| 专题 | 论文数 | 搜索类别数 | 时间范围 |
|------|--------|-----------|---------|
| `arxiv.prompt` | 4,780 | — | 2023–2026 |
| `arxiv.agi-scifi` | 13,606 | 52 | 2023–2026 |
| `arxiv.agent-skills` | 2,606 | 14 | 2000–2026 |
| `arxiv.game-dev` | 5,197 | 29 | 1996–2026 |
| `arxiv.ai-human-future` | 1,814 | 12 | 无限制 |
| `arxiv.qbio-health` | 1,125 | 7 | 无限制 |
| `arxiv.game-dev-with-ai` | 73 | 25 | 2013–2026 |
| `arxiv.software-engineering` | 4,418 | 42 | 2020–2026 |
| `arxiv.qa-quality-engineering` | 3,069 | 35 | 2020–2026 |
| `arxiv.agent-harness` | 2,177 | 42 | 2020–2026 |
| `arxiv.anthropic-claude` | 2,628 | 35 | 2021–2026 |
| `arxiv.child-development` | 5,072 | 37 | 2010–2026 |
| `arxiv.us-stock-market` | 1,241 | 24 | 2010–2026 |
| **合计** | **~47,806** | **345+** | |
