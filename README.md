# arxiv.abs — AI/LLM Prompt Engineering Paper Abstracts

**4780+ curated arXiv paper abstracts on AI/LLM Prompt Engineering (2023–2026), with a structured summary of 50 core techniques.**

**4780+ 篇 AI/LLM 提示词工程 arXiv 论文摘要精选（2023–2026），含 50 项核心技巧结构化总结。**

---

## Why This Repo? / 为什么需要这个仓库？

Prompt engineering research is exploding — over **5000 papers** on arXiv in just 4 years. Finding what matters is hard. This repo saves you hundreds of hours by providing:

提示词工程研究正在爆炸式增长 — 4 年内仅 arXiv 就有超过 **5000 篇**论文。找到真正有价值的内容很难。这个仓库帮你节省数百小时：

- **4780 filtered abstracts** — non-LLM papers (vision, speech, graph) removed
- **50 core techniques** — distilled into a single structured reference
- **Organized by year** — easy to track research trends
- **Categorized by use-case** — reasoning, optimization, security, attacks

- **4780 篇筛选摘要** — 已移除非 LLM 论文（视觉、语音、图等）
- **50 项核心技巧** — 浓缩为一份结构化参考手册
- **按年份组织** — 方便追踪研究趋势
- **按用途分类** — 推理、优化、安全、攻击

---

## Quick Stats / 数据概览

| | Papers / 论文数 |
|------|--------|
| 2023 | 1,085 |
| 2024 | 1,478 |
| 2025 | 1,817 |
| 2026 | 400 |
| **Total** | **4,780** |

---

## Repo Structure / 仓库结构

```
arxiv.prompt/
├── prompt_ai.md                   # 50 core techniques summary / 50 项核心技巧总结
├── 2023/
│   ├── arxiv-results-2023.json    # metadata: titles, authors, abstracts, citations
│   └── abstracts/                 # 1,085 .txt files
├── 2024/
│   ├── arxiv-results-2024.json
│   └── abstracts/                 # 1,478 .txt files
├── 2025/
│   ├── arxiv-results-2025.json
│   └── abstracts/                 # 1,817 .txt files
└── 2026/
    ├── arxiv-results-2026.json
    └── abstracts/                 # 400 .txt files
```

---

## 50 Core Techniques / 50 项核心技巧

Full details in [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md). Here's the overview:

完整内容见 [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md)，以下是概览：

### I. Reasoning & Chain-of-Thought / 推理与思维链 (1–6)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 1 | Chain-of-Thought (CoT) | arXiv:2402.10200 | 238 |
| 2 | Plan-and-Solve Prompting | arXiv:2305.04091 | 640 |
| 3 | Structured CoT for Code | arXiv:2305.06599 | 286 |
| 4 | CoT Separator Enhancement | arXiv:2402.10645 | — |
| 5 | Robust CoT (Noisy Rationales) | arXiv:2410.23856 | 51 |
| 6 | Reasoning Without Prompting | arXiv:2402.10200 | 238 |

### II. Examples & In-Context Learning / 示例与上下文学习 (7–11)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 7 | Few-Shot / ICL | arXiv:2410.02185 | — |
| 8 | Auto-Demo Prompting | arXiv:2410.01724 | — |
| 9 | Mixture-of-Expert Prompts | arXiv:2407.00256 | — |
| 10 | Self-Consistency | arXiv:2402.19371 | 82 |
| 11 | Multi-Prompt Evaluation | arXiv:2401.00595 | 264 |

### III. Prompt Design & Formatting / 设计与格式 (12–16)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 12 | Prompt Pattern Catalog | arXiv:2302.11382 | **1,646** |
| 13 | Prompt Formatting Impact | arXiv:2310.11324 | 626 |
| 14 | Role-Play Prompting | arXiv:2308.07702 | 358 |
| 15 | Emotional Stimulus | arXiv:2404.10500 | — |
| 16 | Butterfly Effect of Prompts | arXiv:2401.03729 | 98 |

### IV. Orchestration & Workflows / 编排与工作流 (17–22)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 17 | Prompt Chaining vs Stepwise | arXiv:2406.00507 | 35 |
| 18 | Meta-Prompting | arXiv:2401.12954 | 132 |
| 19 | Prompt Ensemble | arXiv:2405.07467 | 105 |
| 20 | Flow Engineering for Code | arXiv:2401.08500 | 112 |
| 21 | Prompt Programming (DSL) | arXiv:2406.13161 | — |
| 22 | Multi-Agent Design | arXiv:2502.02533 | 64 |

### V. Optimization & Compression / 优化与压缩 (23–28)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 23 | Auto Prompt Optimization | arXiv:2305.03495 | 591 |
| 24 | Prompt Compression | arXiv:2310.06839 | 371 |
| 25 | Prompt Rewriting | arXiv:2410.20788 | — |
| 26 | Prompt + Fine-Tuning | arXiv:2407.10930 | 40 |
| 27 | Self-Supervised Optimization | arXiv:2502.06855 | 29 |
| 28 | Soft Prompt Tuning | arXiv:2405.15282 | — |

### VI. Quality & Robustness / 质量与鲁棒性 (29–33)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 29 | Prompt Bias Calibration | arXiv:2403.09963 | 25 |
| 30 | Sensitivity Assessment | arXiv:2306.04528 | 246 |
| 31 | Perturbation Consistency | arXiv:2402.15833 | — |
| 32 | LLM-as-a-Judge | arXiv:2408.13006 | 69 |
| 33 | Domain-Specific Prompting | arXiv:2402.19371 | 82 |

### VII. Defense & Protection / 防御与保护 (34–41)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 34 | Spotlighting (Data Marking) | arXiv:2403.14720 | 133 |
| 35 | Structured Query Defense | arXiv:2402.06363 | 207 |
| 36 | Preference-Based Defense | arXiv:2410.05451 | 89 |
| 37 | Injection Detection | arXiv:2507.15219 | 51 |
| 38 | Injection-Immune Architecture | arXiv:2503.18813 | 95 |
| 39 | Multi-Agent Security | arXiv:2502.05174 | 29 |
| 40 | Prompt Theft Protection | arXiv:2412.13426 | — |
| 41 | Unlearning & Caching | arXiv:2406.07933 | 101 |

### VIII. Attacks & Penetration (Security Research) / 攻击与渗透 (42–50)

| # | Technique | Key Paper | Citations |
|---|-----------|-----------|-----------|
| 42 | Indirect Prompt Injection | arXiv:2302.12173 | 989 |
| 43 | Manual Jailbreak Templates | arXiv:2308.03825 | 535 |
| 44 | Automated Jailbreak (AutoDAN) | arXiv:2310.04451 | 658 |
| 45 | Prompt Decomposition Attack | arXiv:2402.16914 | 100 |
| 46 | Sequential Chain Attack | arXiv:2411.06426 | 13 |
| 47 | Prompt Extraction/Stealing | arXiv:2405.06823 | 127 |
| 48 | Learned Injection Triggers | arXiv:2403.03792 | 66 |
| 49 | Adaptive Attacks on Defenses | arXiv:2503.00061 | 61 |
| 50 | Injection Formalization | arXiv:2310.12815 | 263 |

---

## How to Use / 如何使用

**Read the summary / 阅读总结：**

Start with [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md) — it contains all 50 techniques with templates, principles, sources, and use cases.

从 [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md) 开始 — 包含全部 50 项技巧的模板、原理、来源和适用场景。

**Browse abstracts / 浏览摘要：**

Each `.txt` file contains: Title, Authors, arXiv ID, URL, and Abstract — all wrapped to 80 characters per line.

每个 `.txt` 文件包含：标题、作者、arXiv ID、链接和摘要 — 每行不超过 80 字符。

**Use the JSON metadata / 使用 JSON 元数据：**

Each year folder has an `arxiv-results-YYYY.json` with full metadata (title, authors, abstract, categories, citations, URLs) for programmatic access.

每个年份文件夹下有 `arxiv-results-YYYY.json`，包含完整元数据（标题、作者、摘要、分类、引用、链接），方便程序化使用。

---

## Methodology / 方法论

1. **Search** — queried arXiv API for CS papers with "prompt" in title (2023–2026)
2. **Download** — retrieved 5,362 abstracts via [arxs](https://github.com/host452b/arxs) CLI tool
3. **Filter** — removed 582 non-LLM papers (vision prompt tuning, speech, graph neural networks, diffusion models, medical imaging, etc.)
4. **Analyze** — categorized 4,780 papers into fine-grained topics using keyword and citation analysis
5. **Synthesize** — distilled 50 core techniques from top-cited and representative papers

---

## Contributing / 贡献

Issues and PRs welcome! Especially for: / 欢迎提 Issue 和 PR，特别是：

- Suggesting missing techniques / 补充遗漏的技巧
- Correcting categorizations / 纠正分类
- Adding new year data / 添加新年份数据
- Improving the summary / 改进总结内容

---

## License / 许可

The abstracts are sourced from [arXiv](https://arxiv.org/) under their [Terms of Use](https://arxiv.org/help/api/tou). Thank you to arXiv for use of its open access interoperability.

摘要来源于 [arXiv](https://arxiv.org/)，遵循其[使用条款](https://arxiv.org/help/api/tou)。感谢 arXiv 提供开放获取互操作性。

---

## Star History

If this repo helps your research or work, please give it a star! ⭐

如果这个仓库对你的研究或工作有帮助，请给一个 star！⭐
