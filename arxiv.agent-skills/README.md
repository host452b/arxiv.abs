# arxiv.agent-skills — AI Agent Skills: Full Technical Landscape

**2,606 arXiv abstracts** from 14 targeted searches in the CS category, systematically covering the core skill techniques in AI Agent research.

**Core question:** Which skill combinations deliver the maximum task capability gain at minimum engineering cost?

## Search Topics

| # | Skill Category | Keywords | Papers | File |
|---|---------------|----------|--------|------|
| 01 | Reasoning | chain of thought / tree of thought / ReAct / self reflection | 200 | [01-reasoning.json](search-results/01-reasoning.json) |
| 02 | Memory | agent memory / episodic memory / working memory / memory augmented | 200 | [02-memory.json](search-results/02-memory.json) |
| 03 | Tool Use | tool use / function calling / tool augmented / API agent / tool learning | 200 | [03-tool-use.json](search-results/03-tool-use.json) |
| 04 | Planning | task planning / task decomposition / hierarchical planning / goal decomposition | 200 | [04-planning.json](search-results/04-planning.json) |
| 05 | Multi-Agent | multi agent / multiagent cooperation / agent coordination / agent collaboration | 200 | [05-multiagent.json](search-results/05-multiagent.json) |
| 06 | Code Agents | code agent / software agent / coding agent / SWE agent / autonomous coding | 200 | [06-code-agents.json](search-results/06-code-agents.json) |
| 07 | RAG / Retrieval | retrieval augmented agent / knowledge retrieval agent / RAG agent | 200 | [07-rag-retrieval.json](search-results/07-rag-retrieval.json) |
| 08 | Agent Evaluation | agent benchmark / agent evaluation / LLM agent benchmark | 200 | [08-agent-eval.json](search-results/08-agent-eval.json) |
| 09 | Agent Safety | agent safety / agent alignment / agent oversight / LLM agent attack | 200 | [09-agent-safety.json](search-results/09-agent-safety.json) |
| 10 | Embodied AI | embodied agent / embodied AI / grounded agent / physical agent | 200 | [10-embodied.json](search-results/10-embodied.json) |
| 11 | Agent Architecture | LLM agent / autonomous agent architecture / agentic framework | 200 | [11-agent-arch.json](search-results/11-agent-arch.json) |
| 12 | Self-Improvement | self improvement agent / self refinement / self correction / iterative refinement | 200 | [12-self-improve.json](search-results/12-self-improve.json) |
| 13 | Roleplay | role playing agent / persona agent / character simulation / roleplay LLM | 116 | [13-roleplay.json](search-results/13-roleplay.json) |
| 14 | Long-Horizon | long horizon agent / autonomous agent task / web agent / computer agent | 200 | [14-long-horizon.json](search-results/14-long-horizon.json) |

**2,716 raw results → 2,606 deduplicated abstracts**

## Key Findings Summary

> Full analysis in [agent-skills-findings.zh-CN.md](agent-skills-findings.zh-CN.md)

### Critical Quantitative Data (sampled from abstracts)

| Data | Source | Significance |
|------|--------|-------------|
| **+34% ALFWorld / +10% WebShop** | Yao et al. 2022, [arXiv:2210.03629](https://arxiv.org/abs/2210.03629) | ReAct reasoning-acting framework vs. pure RL |
| **3.3x items / 15.3x milestones** | Wang et al. 2023, [arXiv:2305.16291](https://arxiv.org/abs/2305.16291) | Voyager skill library compounds embodied agent ability |
| **SWE-bench 12.5% / HumanEvalFix 87.7%** | Yang et al. 2024, [arXiv:2405.15793](https://arxiv.org/abs/2405.15793) | ACI design determines code agent performance ceiling |
| **Humans 72.36% vs AI 12.24%** | Xie et al. 2024, [arXiv:2404.07972](https://arxiv.org/abs/2404.07972) | OSWorld GUI grounding gap (6× human advantage) |
| **Mind2Web +24.6% / WebArena +51.1%** | Wang et al. 2024, [arXiv:2409.07429](https://arxiv.org/abs/2409.07429) | Agent Workflow Memory relative improvement range |
| **Outperforms ChatGPT (QA/reasoning/facts)** | Asai et al. 2023, [arXiv:2310.11511](https://arxiv.org/abs/2310.11511) | Self-RAG adaptive retrieval vs. fixed retrieval |

### Skills × Engineering Objective Matrix

> ✅ Strong evidence; ⭕ Partial evidence; ⬜ Under-researched

| Skill Type | Reasoning Quality | Task Completion | Context Mgmt | Multi-step Planning | Real-world Grounding | Safety |
|-----------|-----------------|----------------|-------------|--------------------|--------------------|--------|
| **Reasoning (CoT/ReAct)** | ✅ | ✅ | ⭕ | ✅ | ⭕ | ⬜ |
| **Memory (workflow/episodic)** | ⭕ | ✅ | ✅ | ✅ | ⭕ | ⬜ |
| **Tool Use** | ⭕ | ✅ | ⬜ | ⭕ | ✅ | ⭕ |
| **Task Planning** | ✅ | ✅ | ⭕ | ✅ | ⬜ | ⬜ |
| **Multi-Agent** | ⭕ | ✅ | ⭕ | ✅ | ⬜ | ⭕ |
| **Code Agents** | ⭕ | ✅ | ⭕ | ✅ | ✅ | ⭕ |
| **RAG / Retrieval** | ✅ | ✅ | ✅ | ⬜ | ⭕ | ⭕ |
| **Self-Improvement** | ✅ | ✅ | ⭕ | ⭕ | ⬜ | ⭕ |
| **Embodied AI** | ⬜ | ⭕ | ⬜ | ⭕ | ✅ | ⭕ |

### Pareto 20/80 Core Conclusion

**20% of skills drive 80% of capability improvement:**

```
Priority 1 — Reasoning Framework (ReAct / CoT)
  Interleaved reasoning and acting: the foundational lever for all agent tasks
  ALFWorld: +34% | WebShop: +10% vs. pure RL

Priority 2 — Workflow Memory (AWM)
  Inducing reusable routines from past tasks; eliminates redundant exploration
  Mind2Web: +24.6% | WebArena: +51.1% relative improvement

Priority 3 — ACI Interface Design (SWE-agent paradigm)
  Build agent-specific interfaces rather than using human-facing UIs
  SWE-bench: 12.5% (SOTA) | HumanEvalFix: 87.7%
```

### Largest Open Gap

```
GUI Grounding Chasm: Humans 72.36% vs. AI 12.24% (6× gap)
→ OSWorld benchmark, 369 real-world computer tasks
→ Bottleneck: visual grounding + operational knowledge, NOT reasoning or planning
→ Language-domain agent capability does NOT transfer to visual-action domains
```

### Safety Core Tension

The same multi-agent technology creates two opposing failure modes:
- **Hallucination cascades**: single-step errors amplified across multi-agent chains (MetaGPT's SOP design directly addresses this)
- **Over-constrained paralysis**: excessive safety checks severely reduce task success rate

> No universal agent safety solution currently delivers both safety and high performance — the largest engineering open problem in this field.

---

## Abstracts (by Year)

| Year | Papers | Directory |
|------|--------|-----------|
| 2000 | 1 | [2000/abstracts/](2000/abstracts/) |
| 2008–2017 | 57 | 2008–2017/abstracts/ |
| 2018 | 35 | [2018/abstracts/](2018/abstracts/) |
| 2019 | 54 | [2019/abstracts/](2019/abstracts/) |
| 2020 | 79 | [2020/abstracts/](2020/abstracts/) |
| 2021 | 92 | [2021/abstracts/](2021/abstracts/) |
| 2022 | 98 | [2022/abstracts/](2022/abstracts/) |
| 2023 | 179 | [2023/abstracts/](2023/abstracts/) |
| 2024 | 450 | [2024/abstracts/](2024/abstracts/) |
| 2025 | 1117 | [2025/abstracts/](2025/abstracts/) |
| 2026 | 442 | [2026/abstracts/](2026/abstracts/) |

## Search Parameters

- Category: `cs` (Computer Science)
- Sort: `relevance`
- Tool: [arxs](https://github.com/host452b/arxs) v1.0.3

---

[中文说明](README.zh-CN.md) | [Back to main](../README.md)
