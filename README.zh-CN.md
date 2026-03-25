[**English README**](README.md)

# arxiv.abs — arXiv 论文摘要库：AI 研究与科幻世界构建

**29,000+ 篇 arXiv 论文摘要精选，横跨七大专题集（1996–2026），涵盖 AI/LLM 提示词工程、跨学科 AGI/科幻研究、AI Agent 技能、AI 与人类未来、健康科学、游戏开发以及人 × AI 协作开发新范式。**

---

## 专题概览

本仓库包含七大精选论文摘要集：

| 专题 | 论文数 | 类别数 | 时间范围 |
|------|--------|--------|---------|
| [`arxiv.prompt`](arxiv.prompt/) | 4,780 | 8 章节 | 2023–2026 |
| [`arxiv.agi-scifi`](arxiv.agi-scifi/) | 13,606 | 52 主题 | 2023–2026 |
| [`arxiv.agent-skills`](arxiv.agent-skills/) | 2,606 | 14 技能 | 2000–2026 |
| [`arxiv.game-dev`](arxiv.game-dev/) | 5,197 | 29 类别 | 1996–2026 |
| [`arxiv.ai-human-future`](arxiv.ai-human-future/) | 1,814 | 12 主题 | 无限制 |
| [`arxiv.qbio-health`](arxiv.qbio-health/) | 1,125 | 7 主题 | 无限制 |
| [`arxiv.game-dev-with-ai`](arxiv.game-dev-with-ai/) | 73 | 25 类别 | 2013–2026 |
| **合计** | **29,201** | **139+** | |

---

### 1. `arxiv.prompt` — AI/LLM 提示词工程

4,780 篇筛选摘要 + 50 项核心技巧总结。

**主题：** 思维链、少样本/上下文学习、提示优化、压缩、越狱/注入、防御、多智能体、角色扮演、自一致性等。

### 2. `arxiv.agi-scifi` — 跨学科 AGI 与科幻研究

13,606 篇摘要，来自 52 组关键词搜索，横跨 arXiv 全学科 — 物理、数学、计算机、生物、经济等。

**52 组搜索主题涵盖：**

| 分类 | 主题 |
|------|------|
| **AGI 与智能** | AGI/超级智能、AI 意识、涌现、缩放定律、自我改进 AI、神经符号 AI |
| **安全与治理** | AI 对齐/安全、AI 欺骗、AI 治理、AI 军事/武器、存在性风险 |
| **社会与经济** | AI + 经济/社会、未来工作、后稀缺、人机关系 |
| **物理与宇宙** | AI + 宇宙学、引力物理、奇异物理、量子引力、量子计算、万有理论 |
| **太空与外星生存** | AI + 太空、星际旅行、太空栖息地、地球改造、SETI/费米悖论、技术信号、外星生命、极端微生物、生命起源 |
| **能源与硬件** | AI + 核能/聚变、AI + 气候、AI 硬件/神经形态 |
| **科学与发现** | AI for Science、AI + 生物/长寿、AI + 科学发现、AI + 数学基础 |
| **架构与系统** | 世界模型、AI Agent、具身智能、集体智能、去中心化 AI、开放式进化 |
| **心智与前沿** | 奇点/脑机接口、意识上传、模拟/虚拟世界、AI 创造力、AI 编程、AI 幻觉、巨构/戴森球 |
| **生命维持** | 生命维持系统、原位资源利用 (ISRU) |

### 3. `arxiv.agent-skills` — AI Agent 技能与能力

2,606 篇摘要，覆盖 14 项核心 AI Agent 技能：推理、记忆、工具使用、规划、多智能体协作、代码 Agent、RAG、评估、安全、具身 AI、架构、自我改进、角色扮演、长时域任务。

### 4. `arxiv.game-dev` — 游戏开发研究（经典）

5,197 篇摘要，来自 29 个类别，覆盖学术游戏开发研究全史（1996–2026）：PCG、游戏 AI、自动测试、游戏设计、图形、音频等。

### 5. `arxiv.ai-human-future` — AI 与人类未来

1,814 篇摘要，聚焦 12 个人类-AI 协同进化前沿主题：生物进化 × AI、后人类未来、意识上传、脑机接口、社会转型等。

### 6. `arxiv.qbio-health` — 定量生物学与健康科学

1,125 篇摘要，涵盖 7 个循证健康主题：衰老与长寿、饮食与代谢、运动、睡眠与昼夜节律、肠道菌群、死亡率风险因素、补充剂。

### 7. `arxiv.game-dev-with-ai` — 人 × AI 协作开发（新时代）

73 篇精选摘要（从 542 篇原始结果中过滤），来自 25 组定向搜索，聚焦 AI 成为游戏开发**协同开发者和创意伙伴**的新兴领域。涵盖 LLM 辅助设计、共创系统、生成式资产、自主游戏设计等。

---

## 专题集格式规范

所有子专题集遵循统一格式标准，详见 **[STANDARDS.md](STANDARDS.md)**。

**核心要求：** 每个专题集 README 中的每个类别或分段，都必须包含「**二八定律（80/20）核心最佳实践总结**」——找出该领域 20% 的关键实践，说明其如何覆盖 80% 的效果。

---

## 仓库结构

```
arxiv.abs/
├── README.md                              # 英文版
├── README.zh-CN.md                        # 中文版
├── STANDARDS.md                           # 专题集格式规范
├── arxiv.prompt/                          # 提示词工程（4,780 篇）
│   ├── README.md / README.zh-CN.md
│   ├── prompt_ai.md / prompt_ai.zh-CN.md  # 50 项核心技巧
│   └── 2023–2026/abstracts/
├── arxiv.agi-scifi/                       # AGI 与科幻研究（13,606 篇）
│   ├── README.md / README.zh-CN.md
│   ├── agi-scifi.md / agi-scifi.zh-CN.md  # 核心发现
│   ├── search-index.json
│   └── 2023–2026/abstracts/
├── arxiv.agent-skills/                    # AI Agent 技能（2,606 篇）
│   ├── README.md / README.zh-CN.md
│   ├── agent-skills-findings.zh-CN.md
│   ├── search-index.json
│   └── 2000–2026/abstracts/
├── arxiv.game-dev/                        # 游戏开发经典（5,197 篇）
│   ├── README.md / README.zh-CN.md
│   ├── readme_game_roadmap.md
│   ├── search-index.json
│   └── 1996–2026/abstracts/
├── arxiv.ai-human-future/                 # AI 与人类未来（1,814 篇）
│   ├── README.md / README.zh-CN.md
│   ├── ai-future-findings.zh-CN.md
│   ├── search-index.json
│   └── abstracts/
├── arxiv.qbio-health/                     # 健康科学（1,125 篇）
│   ├── README.md / README.zh-CN.md
│   ├── health-findings.zh-CN.md
│   ├── search-index.json
│   └── abstracts/
└── arxiv.game-dev-with-ai/                # 人 × AI 协作开发（348 篇）
    ├── README.md / README.zh-CN.md
    ├── readme_game_dev_with_ai.md          # 全景分析与实践路线图
    ├── search-index.json
    └── 2005–2026/abstracts/
```

---

## 快速开始

**浏览提示词技巧：**

从 [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md) 开始 — 50 项技巧含模板、原理、来源和适用场景。

**探索科幻研究素材：**

浏览 `arxiv.agi-scifi/` 年份目录 — 每篇摘要是独立 `.txt` 文件，含标题、作者、arXiv ID 和摘要正文。

**程序化访问：**

```python
import json

data = json.load(open("arxiv.agi-scifi/2025/arxiv-results-2025.json"))
for paper in data["papers"]:
    print(paper["title"], paper["categories"], paper.get("citations", "N/A"))
```

---

## 方法论

### 提示词工程专题

1. 通过 arXiv API 搜索标题含 "prompt" 的 CS 论文（2023–2026）
2. 使用 [arxs](https://github.com/host452b/arxs) CLI 工具下载 5,362 篇摘要
3. 过滤掉 582 篇非 LLM 论文（视觉、语音、图、扩散模型、医学影像等）
4. 对 4,780 篇论文分类并提炼 50 项核心技巧

### AGI/科幻研究专题

1. 设计 52 组跨学科关键词搜索，覆盖 arXiv 全部类别
2. 获取 14,520 条原始结果，涵盖物理、数学、计算机、生物、经济等
3. 去重后得到 13,606 篇唯一论文
4. 按年份组织，摘要格式化为每行 80 字符

---

## 50 项提示词核心技巧

完整内容见 [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md)：

| 章节 | 技巧 | 编号 |
|------|------|------|
| I. 推理与思维链 | CoT、Plan-and-Solve、结构化 CoT 等 | #1–6 |
| II. 示例与上下文学习 | Few-Shot、Auto-Demo、Self-Consistency 等 | #7–11 |
| III. 设计与格式 | Pattern Catalog、角色扮演、情感刺激等 | #12–16 |
| IV. 编排与工作流 | Chaining、Meta-Prompting、多智能体等 | #17–22 |
| V. 优化与压缩 | 自动优化、压缩、Soft Prompt 等 | #23–28 |
| VI. 质量与鲁棒性 | 偏差校准、敏感性、LLM-as-Judge 等 | #29–33 |
| VII. 防御与保护 | Spotlighting、查询防御、注入检测等 | #34–41 |
| VIII. 攻击与渗透（安全研究） | 越狱、提示注入、提取等 | #42–50 |

---

## 52 组科幻研究搜索关键词

<details>
<summary>点击展开完整搜索列表</summary>

| # | 搜索主题 | 论文数 |
|---|---------|--------|
| 01 | AGI / 超级智能 | 434 |
| 02 | AI + 经济 / 社会 | 500 |
| 03 | AI + 宇宙学 / 宇宙 | 500 |
| 04 | AI 意识 | 51 |
| 05 | 人机关系 | 500 |
| 06 | AI + 核能 | 195 |
| 07 | AI 安全 / 对齐 | 500 |
| 08 | AI 治理 | 423 |
| 09 | AI + 太空探索 | 500 |
| 10 | AI + 数学基础 | 26 |
| 11 | AI + 量子计算 | 500 |
| 12 | 奇点 / 脑机接口 | 239 |
| 13 | AI 中的涌现 | 500 |
| 14 | AI + 军事 / 武器 | 22 |
| 15 | 世界模型 | 500 |
| 16 | 自我改进 AI | 268 |
| 17 | AI + 气候 / 能源 | 500 |
| 18 | AI + 生物 / 长寿 | 460 |
| 19 | 集体智能 | 500 |
| 20 | 模拟 / 虚拟世界 | 500 |
| 21 | 神经符号 AI | 500 |
| 22 | AI + 科学发现 | 261 |
| 23 | 去中心化 AI | 252 |
| 24 | AI + 创造力 / 艺术 | 365 |
| 25 | AI 自主 Agent | 500 |
| 26 | 具身智能 | 500 |
| 27 | 巨构 / 戴森球 | 20 |
| 28 | AI for Science | 194 |
| 29 | SETI / 费米悖论 | 57 |
| 30 | 信息论 + 智能 | 500 |
| 31 | 未来工作 | 500 |
| 32 | 意识上传 | 18 |
| 33 | 缩放定律 | 500 |
| 34 | AI 欺骗 / 失控 | 63 |
| 35 | AI + 引力物理 | 302 |
| 36 | 后稀缺经济 | 7 |
| 37 | 万有理论 | 39 |
| 38 | AI 硬件 / 神经形态 | 500 |
| 39 | AI + 奇异物理 | 124 |
| 40 | AI + 聚变控制 | 44 |
| 41 | AI 代码生成 | 355 |
| 42 | AI 幻觉 / 信任 | 307 |
| 43 | 开放式进化 | 189 |
| 44 | 量子引力 + 信息 | 322 |
| 45 | 外星生命 / 天体生物学 | 199 |
| 46 | 太空栖息地 / 殖民 | 83 |
| 47 | 生命维持系统 / ISRU | 9 |
| 48 | 极端微生物 / 太空生物学 | 54 |
| 49 | 星际旅行 / 推进 | 55 |
| 50 | 地球改造 | 11 |
| 51 | 生命起源 / 泛种论 | 20 |
| 52 | 技术信号 / 宇宙考古 | 52 |

</details>

---

## 适用场景

- **提示词工程师** — 查找和应用最新 LLM 提示技巧
- **AI 安全研究者** — 研究对齐、欺骗、越狱和防御
- **科幻作家** — 发现真实科学观点用于世界构建
- **学生和研究者** — 快速浏览跨学科 AI 文献

---

## 贡献

欢迎提 Issue 和 PR！

- 补充遗漏的主题或技巧
- 纠正分类
- 添加新搜索关键词
- 改进总结

---

## 许可

摘要来源于 [arXiv](https://arxiv.org/)，遵循其[使用条款](https://arxiv.org/help/api/tou)。感谢 arXiv 提供开放获取互操作性。

---

如果这个仓库对你有帮助，请点个 star！⭐
