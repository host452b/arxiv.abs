# arxiv.abs — arXiv Paper Abstracts for AI Research & Sci-Fi Worldbuilding

**18,000+ curated arXiv paper abstracts across two collections (2023–2026), covering AI/LLM Prompt Engineering and cross-disciplinary AGI/Sci-Fi research.**

**18,000+ 篇 arXiv 论文摘要精选，横跨两大专题集（2023–2026），涵盖 AI/LLM 提示词工程与跨学科 AGI/科幻研究。**

---

## Collections Overview / 专题概览

This repository contains two curated paper abstract collections:

本仓库包含两个精选论文摘要集：

### 1. `arxiv.prompt` — AI/LLM Prompt Engineering / 提示词工程

4,780 filtered abstracts + 50 core techniques summary.

4,780 篇筛选摘要 + 50 项核心技巧总结。

| Year | Papers |
|------|--------|
| 2023 | 1,085 |
| 2024 | 1,478 |
| 2025 | 1,817 |
| 2026 | 400 |
| **Total** | **4,780** |

**Topics:** Chain-of-Thought, Few-Shot/ICL, Prompt Optimization, Compression, Jailbreak/Injection, Defense, Multi-Agent, Role-Play, Self-Consistency, and more.

**主题：** 思维链、少样本/上下文学习、提示优化、压缩、越狱/注入、防御、多智能体、角色扮演、自一致性等。

### 2. `arxiv.agi-scifi` — Cross-Disciplinary AGI & Sci-Fi Research / 跨学科 AGI 与科幻研究

13,606 abstracts from 52 keyword searches across all arXiv categories — physics, math, CS, biology, economics, and more.

13,606 篇摘要，来自 52 组关键词搜索，横跨 arXiv 全学科 — 物理、数学、计算机、生物、经济等。

| Year | Papers |
|------|--------|
| 2023 | 2,679 |
| 2024 | 3,761 |
| 2025 | 5,641 |
| 2026 | 1,525 |
| **Total** | **13,606** |

**52 search topics spanning:** / **52 组搜索主题涵盖：**

| Category | Topics / 主题 |
|----------|---------------|
| **AGI & Intelligence** | AGI/Superintelligence, AI Consciousness, Emergence, Scaling Laws, Self-Improving AI, Neuro-Symbolic AI |
| **AGI 与智能** | AGI/超级智能、AI 意识、涌现、缩放定律、自我改进 AI、神经符号 AI |
| **Safety & Governance** | AI Alignment/Safety, AI Deception, AI Governance, AI Military/Weapons, Existential Risk |
| **安全与治理** | AI 对齐/安全、AI 欺骗、AI 治理、AI 军事/武器、存在性风险 |
| **Society & Economy** | AI + Economy/Society, Future of Work, Post-Scarcity, Human-AI Relationship |
| **社会与经济** | AI + 经济/社会、未来工作、后稀缺、人机关系 |
| **Physics & Universe** | AI + Cosmology, Gravitational Physics, Exotic Physics, Quantum Gravity, Quantum Computing, Theory of Everything |
| **物理与宇宙** | AI + 宇宙学、引力物理、奇异物理、量子引力、量子计算、万有理论 |
| **Space & Extraterrestrial** | AI + Space, Interstellar Travel, Space Habitat, Terraforming, SETI/Fermi Paradox, Technosignature, Extraterrestrial Life, Extremophile, Origin of Life |
| **太空与外星生存** | AI + 太空、星际旅行、太空栖息地、地球改造、SETI/费米悖论、技术信号、外星生命、极端微生物、生命起源 |
| **Energy & Hardware** | AI + Nuclear/Fusion, AI + Climate, AI Hardware/Neuromorphic |
| **能源与硬件** | AI + 核能/聚变、AI + 气候、AI 硬件/神经形态 |
| **Science & Discovery** | AI for Science, AI + Biology/Longevity, AI + Scientific Discovery, AI + Math Foundations |
| **科学与发现** | AI for Science、AI + 生物/长寿、AI + 科学发现、AI + 数学基础 |
| **Architecture & Systems** | World Models, AI Agents, Embodied AI, Collective Intelligence, Decentralized AI, Open-Ended Evolution |
| **架构与系统** | 世界模型、AI Agent、具身智能、集体智能、去中心化 AI、开放式进化 |
| **Mind & Frontier** | Singularity/BCI, Mind Uploading, Simulation/Virtual World, AI Creativity, AI Coding, AI Hallucination, Megastructure/Dyson Sphere |
| **心智与前沿** | 奇点/脑机接口、意识上传、模拟/虚拟世界、AI 创造力、AI 编程、AI 幻觉、巨构/戴森球 |
| **Life Support** | Life Support Systems, ISRU |
| **生命维持** | 生命维持系统、原位资源利用 |

---

## Repo Structure / 仓库结构

```
arxiv.abs/
├── README.md
├── arxiv.prompt/                          # prompt engineering collection
│   ├── prompt_ai.md                       # 50 core techniques summary
│   ├── 2023/
│   │   ├── arxiv-results-2023.json        # metadata
│   │   └── abstracts/                     # 1,085 .txt files
│   ├── 2024/
│   │   ├── arxiv-results-2024.json
│   │   └── abstracts/                     # 1,478 .txt files
│   ├── 2025/
│   │   ├── arxiv-results-2025.json
│   │   └── abstracts/                     # 1,817 .txt files
│   └── 2026/
│       ├── arxiv-results-2026.json
│       └── abstracts/                     # 400 .txt files
└── arxiv.agi-scifi/                       # AGI & sci-fi collection
    ├── search-index.json                  # 52 search queries metadata
    ├── 2023/
    │   ├── arxiv-results-2023.json        # 2,679 papers metadata
    │   └── abstracts/                     # 2,679 .txt files
    ├── 2024/
    │   ├── arxiv-results-2024.json        # 3,761 papers metadata
    │   └── abstracts/                     # 3,761 .txt files
    ├── 2025/
    │   ├── arxiv-results-2025.json        # 5,641 papers metadata
    │   └── abstracts/                     # 5,641 .txt files
    └── 2026/
        ├── arxiv-results-2026.json        # 1,525 papers metadata
        └── abstracts/                     # 1,525 .txt files
```

---

## Quick Start / 快速开始

**Browse the prompt techniques / 浏览提示词技巧：**

Start with [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md) — 50 techniques with templates, principles, sources, and use cases.

从 [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md) 开始 — 50 项技巧含模板、原理、来源和适用场景。

**Explore sci-fi research / 探索科幻研究素材：**

Browse the `arxiv.agi-scifi/` directory by year — each abstract is a self-contained `.txt` file with title, authors, arXiv ID, and abstract text.

浏览 `arxiv.agi-scifi/` 年份目录 — 每篇摘要是独立 `.txt` 文件，含标题、作者、arXiv ID 和摘要正文。

**Programmatic access / 程序化访问：**

```python
import json

data = json.load(open("arxiv.agi-scifi/2025/arxiv-results-2025.json"))
for paper in data["papers"]:
    print(paper["title"], paper["categories"], paper.get("citations", "N/A"))
```

---

## Methodology / 方法论

### Prompt Collection / 提示词工程专题

1. Searched arXiv API for CS papers with "prompt" in title (2023–2026)
2. Retrieved 5,362 abstracts via [arxs](https://github.com/host452b/arxs) CLI tool
3. Filtered out 582 non-LLM papers (vision, speech, graph, diffusion, medical)
4. Categorized 4,780 papers and distilled 50 core techniques

### AGI/Sci-Fi Collection / AGI/科幻研究专题

1. Designed 52 cross-disciplinary keyword searches across all arXiv categories
2. Retrieved 14,520 raw results covering physics, math, CS, biology, economics, etc.
3. Deduplicated to 13,606 unique papers
4. Organized by year with formatted abstracts (80 chars/line)

---

## 50 Prompt Engineering Techniques / 50 项提示词核心技巧

Full details in [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md):

| Section | Techniques | Range |
|---------|------------|-------|
| I. Reasoning & CoT / 推理与思维链 | CoT, Plan-and-Solve, Structured CoT, etc. | #1–6 |
| II. Examples & ICL / 示例与上下文学习 | Few-Shot, Auto-Demo, Self-Consistency, etc. | #7–11 |
| III. Design & Formatting / 设计与格式 | Pattern Catalog, Role-Play, Emotional Stimulus, etc. | #12–16 |
| IV. Orchestration / 编排与工作流 | Chaining, Meta-Prompting, Multi-Agent, etc. | #17–22 |
| V. Optimization / 优化与压缩 | Auto Optimization, Compression, Soft Prompt, etc. | #23–28 |
| VI. Quality & Robustness / 质量与鲁棒性 | Bias Calibration, Sensitivity, LLM-as-Judge, etc. | #29–33 |
| VII. Defense / 防御与保护 | Spotlighting, Query Defense, Injection Detection, etc. | #34–41 |
| VIII. Attacks (Research) / 攻击与渗透 | Jailbreak, Prompt Injection, Extraction, etc. | #42–50 |

---

## 52 AGI/Sci-Fi Search Keywords / 52 组科幻研究搜索关键词

<details>
<summary>Click to expand full search list / 点击展开完整搜索列表</summary>

| # | Search Topic | Papers |
|---|-------------|--------|
| 01 | AGI / Superintelligence | 434 |
| 02 | AI + Economy / Society | 500 |
| 03 | AI + Cosmology / Universe | 500 |
| 04 | AI Consciousness | 51 |
| 05 | Human-AI Relationship | 500 |
| 06 | AI + Nuclear Energy | 195 |
| 07 | AI Safety / Alignment | 500 |
| 08 | AI Governance | 423 |
| 09 | AI + Space Exploration | 500 |
| 10 | AI + Math Foundations | 26 |
| 11 | AI + Quantum Computing | 500 |
| 12 | Singularity / BCI | 239 |
| 13 | Emergence in AI | 500 |
| 14 | AI + Military / Weapons | 22 |
| 15 | World Models | 500 |
| 16 | Self-Improving AI | 268 |
| 17 | AI + Climate / Energy | 500 |
| 18 | AI + Biology / Longevity | 460 |
| 19 | Collective Intelligence | 500 |
| 20 | Simulation / Virtual World | 500 |
| 21 | Neuro-Symbolic AI | 500 |
| 22 | AI + Scientific Discovery | 261 |
| 23 | Decentralized AI | 252 |
| 24 | AI + Creativity / Art | 365 |
| 25 | AI Autonomous Agents | 500 |
| 26 | Embodied AI | 500 |
| 27 | Megastructure / Dyson Sphere | 20 |
| 28 | AI for Science | 194 |
| 29 | SETI / Fermi Paradox | 57 |
| 30 | Information Theory + Intelligence | 500 |
| 31 | Future of Work | 500 |
| 32 | Mind Uploading | 18 |
| 33 | Scaling Laws | 500 |
| 34 | AI Deception / Misalignment | 63 |
| 35 | AI + Gravitational Physics | 302 |
| 36 | Post-Scarcity Economics | 7 |
| 37 | Theory of Everything | 39 |
| 38 | AI Hardware / Neuromorphic | 500 |
| 39 | AI + Exotic Physics | 124 |
| 40 | AI + Fusion Control | 44 |
| 41 | AI Code Generation | 355 |
| 42 | AI Hallucination / Trust | 307 |
| 43 | Open-Ended Evolution | 189 |
| 44 | Quantum Gravity + Information | 322 |
| 45 | Extraterrestrial Life / Astrobiology | 199 |
| 46 | Space Habitat / Colonization | 83 |
| 47 | Life Support Systems / ISRU | 9 |
| 48 | Extremophile / Space Biology | 54 |
| 49 | Interstellar Travel / Propulsion | 55 |
| 50 | Terraforming | 11 |
| 51 | Origin of Life / Panspermia | 20 |
| 52 | Technosignature / Cosmic Archaeology | 52 |

</details>

---

## Use Cases / 适用场景

- **Prompt engineers** — find and apply the latest LLM prompting techniques
- **AI safety researchers** — study alignment, deception, jailbreak, and defense
- **Sci-fi writers** — discover real scientific ideas for worldbuilding
- **Students & researchers** — quickly survey cross-disciplinary AI literature

- **提示词工程师** — 查找和应用最新 LLM 提示技巧
- **AI 安全研究者** — 研究对齐、欺骗、越狱和防御
- **科幻作家** — 发现真实科学观点用于世界构建
- **学生和研究者** — 快速浏览跨学科 AI 文献

---

## Contributing / 贡献

Issues and PRs welcome! / 欢迎提 Issue 和 PR！

- Suggest missing topics or techniques / 补充遗漏的主题或技巧
- Correct categorizations / 纠正分类
- Add new search keywords / 添加新搜索关键词
- Improve summaries / 改进总结

---

## License / 许可

Abstracts are sourced from [arXiv](https://arxiv.org/) under their [Terms of Use](https://arxiv.org/help/api/tou). Thank you to arXiv for use of its open access interoperability.

摘要来源于 [arXiv](https://arxiv.org/)，遵循其[使用条款](https://arxiv.org/help/api/tou)。感谢 arXiv 提供开放获取互操作性。

---

If this repo helps your research or work, please star it! ⭐

如果这个仓库对你有帮助，请点个 star！⭐
