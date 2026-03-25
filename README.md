[**中文版 README**](README.zh-CN.md)

# arxiv.abs — arXiv Paper Abstracts for AI Research & Sci-Fi Worldbuilding

**29,000+ curated arXiv paper abstracts across six collections (1996–2026), covering AI/LLM Prompt Engineering, cross-disciplinary AGI/Sci-Fi research, AI Agent skills, AI-Human futures, health science, game development, and the emerging field of Human × AI co-development.**

---

## Collections Overview

This repository contains six curated paper abstract collections:

| Collection | Papers | Categories | Years |
|-----------|--------|------------|-------|
| [`arxiv.prompt`](arxiv.prompt/) | 4,780 | 8 sections | 2023–2026 |
| [`arxiv.agi-scifi`](arxiv.agi-scifi/) | 13,606 | 52 topics | 2023–2026 |
| [`arxiv.agent-skills`](arxiv.agent-skills/) | 2,606 | 14 skills | 2000–2026 |
| [`arxiv.game-dev`](arxiv.game-dev/) | 5,197 | 29 categories | 1996–2026 |
| [`arxiv.ai-human-future`](arxiv.ai-human-future/) | 1,814 | 12 topics | unlimited |
| [`arxiv.qbio-health`](arxiv.qbio-health/) | 1,125 | 7 topics | unlimited |
| [`arxiv.game-dev-with-ai`](arxiv.game-dev-with-ai/) | 73 | 25 categories | 2013–2026 |
| **Total** | **29,201** | **139+** | |

---

### 1. `arxiv.prompt` — AI/LLM Prompt Engineering

4,780 filtered abstracts + 50 core techniques summary.

**Topics:** Chain-of-Thought, Few-Shot/ICL, Prompt Optimization, Compression, Jailbreak/Injection, Defense, Multi-Agent, Role-Play, Self-Consistency, and more.

### 2. `arxiv.agi-scifi` — Cross-Disciplinary AGI & Sci-Fi Research

13,606 abstracts from 52 keyword searches across all arXiv categories — physics, math, CS, biology, economics, and more.

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

### 3. `arxiv.agent-skills` — AI Agent Skills & Capabilities

2,606 abstracts covering 14 core AI agent skill categories: Reasoning, Memory, Tool Use, Planning, Multi-Agent Coordination, Code Agents, RAG, Evaluation, Safety, Embodied AI, Architecture, Self-Improvement, Roleplay, and Long-Horizon Tasks.

### 4. `arxiv.game-dev` — Game Development Research (Classical)

5,197 abstracts from 29 categories covering the full history of academic game development research (1996–2026): PCG, game AI, playtesting, game design, graphics, audio, and more.

### 5. `arxiv.ai-human-future` — AI & Human Future

1,814 abstracts on 12 topics at the frontier of human-AI coevolution: biological evolution × AI, posthuman futures, mind uploading, brain-computer interfaces, social transformation, and more.

### 6. `arxiv.qbio-health` — Quantitative Biology & Health Science

1,125 abstracts on 7 evidence-based health topics: aging & longevity, diet & metabolism, exercise, sleep & circadian biology, gut microbiome, mortality risk factors, and supplements.

### 7. `arxiv.game-dev-with-ai` — Human × AI Co-Development (New Era)

73 curated abstracts (filtered from 542 raw) from 25 targeted searches on the emerging field where AI becomes a **co-developer and creative partner** in game development. Covers LLM-assisted design, co-creative systems, generative assets, autonomous game design, and more.

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
├── STANDARDS.md                           # Collection format standards
├── arxiv.prompt/                          # Prompt engineering (4,780 papers)
│   ├── README.md / README.zh-CN.md
│   ├── prompt_ai.md / prompt_ai.zh-CN.md  # 50 core techniques
│   └── 2023–2026/abstracts/
├── arxiv.agi-scifi/                       # AGI & sci-fi (13,606 papers)
│   ├── README.md / README.zh-CN.md
│   ├── agi-scifi.md / agi-scifi.zh-CN.md  # Key findings
│   ├── search-index.json
│   └── 2023–2026/abstracts/
├── arxiv.agent-skills/                    # Agent skills (2,606 papers)
│   ├── README.md / README.zh-CN.md
│   ├── agent-skills-findings.zh-CN.md
│   ├── search-index.json
│   └── 2000–2026/abstracts/
├── arxiv.game-dev/                        # Game dev classical (5,197 papers)
│   ├── README.md / README.zh-CN.md
│   ├── readme_game_roadmap.md
│   ├── search-index.json
│   └── 1996–2026/abstracts/
├── arxiv.ai-human-future/                 # AI-human futures (1,814 papers)
│   ├── README.md / README.zh-CN.md
│   ├── ai-future-findings.zh-CN.md
│   ├── search-index.json
│   └── abstracts/
├── arxiv.qbio-health/                     # Health science (1,125 papers)
│   ├── README.md / README.zh-CN.md
│   ├── health-findings.zh-CN.md
│   ├── search-index.json
│   └── abstracts/
└── arxiv.game-dev-with-ai/                # Human × AI co-dev (73 curated papers)
    ├── README.md / README.zh-CN.md
    ├── readme_game_dev_with_ai.md          # Landscape & practitioner roadmap
    ├── search-index.json
    └── 2005–2026/abstracts/
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
