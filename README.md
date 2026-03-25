[**中文版 README**](README.zh-CN.md)

# arxiv.abs — arXiv Paper Abstracts for AI Research & Sci-Fi Worldbuilding

**18,000+ curated arXiv paper abstracts across two collections (2023–2026), covering AI/LLM Prompt Engineering and cross-disciplinary AGI/Sci-Fi research.**

---

## Collections Overview

This repository contains two curated paper abstract collections:

### 1. `arxiv.prompt` — AI/LLM Prompt Engineering

4,780 filtered abstracts + 50 core techniques summary.

| Year | Papers |
|------|--------|
| 2023 | 1,085 |
| 2024 | 1,478 |
| 2025 | 1,817 |
| 2026 | 400 |
| **Total** | **4,780** |

**Topics:** Chain-of-Thought, Few-Shot/ICL, Prompt Optimization, Compression, Jailbreak/Injection, Defense, Multi-Agent, Role-Play, Self-Consistency, and more.

### 2. `arxiv.agi-scifi` — Cross-Disciplinary AGI & Sci-Fi Research

13,606 abstracts from 52 keyword searches across all arXiv categories — physics, math, CS, biology, economics, and more.

| Year | Papers |
|------|--------|
| 2023 | 2,679 |
| 2024 | 3,761 |
| 2025 | 5,641 |
| 2026 | 1,525 |
| **Total** | **13,606** |

**52 search topics spanning:**

| Category | Topics |
|----------|--------|
| **AGI & Intelligence** | AGI/Superintelligence, AI Consciousness, Emergence, Scaling Laws, Self-Improving AI, Neuro-Symbolic AI |
| **Safety & Governance** | AI Alignment/Safety, AI Deception, AI Governance, AI Military/Weapons, Existential Risk |
| **Society & Economy** | AI + Economy/Society, Future of Work, Post-Scarcity, Human-AI Relationship |
| **Physics & Universe** | AI + Cosmology, Gravitational Physics, Exotic Physics, Quantum Gravity, Quantum Computing, Theory of Everything |
| **Space & Extraterrestrial** | AI + Space, Interstellar Travel, Space Habitat, Terraforming, SETI/Fermi Paradox, Technosignature, Extraterrestrial Life, Extremophile, Origin of Life |
| **Energy & Hardware** | AI + Nuclear/Fusion, AI + Climate, AI Hardware/Neuromorphic |
| **Science & Discovery** | AI for Science, AI + Biology/Longevity, AI + Scientific Discovery, AI + Math Foundations |
| **Architecture & Systems** | World Models, AI Agents, Embodied AI, Collective Intelligence, Decentralized AI, Open-Ended Evolution |
| **Mind & Frontier** | Singularity/BCI, Mind Uploading, Simulation/Virtual World, AI Creativity, AI Coding, AI Hallucination, Megastructure/Dyson Sphere |
| **Life Support** | Life Support Systems, ISRU |

---

## Collection Format Standards

All sub-collections follow a unified format standard. See **[STANDARDS.md](STANDARDS.md)** for the full spec.

**Core requirement:** Every category or segment in every collection README must include an **80/20 Pareto best practices summary** — identifying the 20% of key practices that drive 80% of outcomes in that domain.

---

## Repo Structure

```
arxiv.abs/
├── README.md                              # English
├── README.zh-CN.md                        # Chinese
├── arxiv.prompt/                          # prompt engineering collection
│   ├── README.md                          # directory guide
│   ├── prompt_ai.md                       # 50 core techniques (English)
│   ├── prompt_ai.zh-CN.md                 # 50 core techniques (Chinese)
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
    ├── README.md                          # directory guide
    ├── agi-scifi.md                       # key findings (English)
    ├── agi-scifi.zh-CN.md                 # key findings (Chinese)
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

## Quick Start

**Browse the prompt techniques:**

Start with [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md) — 50 techniques with templates, principles, sources, and use cases.

**Explore sci-fi research:**

Browse the `arxiv.agi-scifi/` directory by year — each abstract is a self-contained `.txt` file with title, authors, arXiv ID, and abstract text.

**Programmatic access:**

```python
import json

data = json.load(open("arxiv.agi-scifi/2025/arxiv-results-2025.json"))
for paper in data["papers"]:
    print(paper["title"], paper["categories"], paper.get("citations", "N/A"))
```

---

## Methodology

### Prompt Collection

1. Searched arXiv API for CS papers with "prompt" in title (2023–2026)
2. Retrieved 5,362 abstracts via [arxs](https://github.com/host452b/arxs) CLI tool
3. Filtered out 582 non-LLM papers (vision, speech, graph, diffusion, medical)
4. Categorized 4,780 papers and distilled 50 core techniques

### AGI/Sci-Fi Collection

1. Designed 52 cross-disciplinary keyword searches across all arXiv categories
2. Retrieved 14,520 raw results covering physics, math, CS, biology, economics, etc.
3. Deduplicated to 13,606 unique papers
4. Organized by year with formatted abstracts (80 chars/line)

---

## 50 Prompt Engineering Techniques

Full details in [`arxiv.prompt/prompt_ai.md`](arxiv.prompt/prompt_ai.md):

| Section | Techniques | Range |
|---------|------------|-------|
| I. Reasoning & CoT | CoT, Plan-and-Solve, Structured CoT, etc. | #1–6 |
| II. Examples & ICL | Few-Shot, Auto-Demo, Self-Consistency, etc. | #7–11 |
| III. Design & Formatting | Pattern Catalog, Role-Play, Emotional Stimulus, etc. | #12–16 |
| IV. Orchestration | Chaining, Meta-Prompting, Multi-Agent, etc. | #17–22 |
| V. Optimization | Auto Optimization, Compression, Soft Prompt, etc. | #23–28 |
| VI. Quality & Robustness | Bias Calibration, Sensitivity, LLM-as-Judge, etc. | #29–33 |
| VII. Defense | Spotlighting, Query Defense, Injection Detection, etc. | #34–41 |
| VIII. Attacks (Research) | Jailbreak, Prompt Injection, Extraction, etc. | #42–50 |

---

## 52 AGI/Sci-Fi Search Keywords

<details>
<summary>Click to expand full search list</summary>

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

## Use Cases

- **Prompt engineers** — find and apply the latest LLM prompting techniques
- **AI safety researchers** — study alignment, deception, jailbreak, and defense
- **Sci-fi writers** — discover real scientific ideas for worldbuilding
- **Students & researchers** — quickly survey cross-disciplinary AI literature

---

## Contributing

Issues and PRs welcome!

- Suggest missing topics or techniques
- Correct categorizations
- Add new search keywords
- Improve summaries

---

## License

Abstracts are sourced from [arXiv](https://arxiv.org/) under their [Terms of Use](https://arxiv.org/help/api/tou). Thank you to arXiv for use of its open access interoperability.

---

If this repo helps your research or work, please star it! ⭐
