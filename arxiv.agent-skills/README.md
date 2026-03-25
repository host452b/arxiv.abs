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

## Best Practices by Category (80/20 Pareto)

> **Pareto Principle:** In each skill domain, 20% of key practices drive 80% of capability improvement. Each lever below reflects the high-frequency consensus from papers in that category.

### 01 Reasoning

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **ReAct (Reasoning + Acting)**: interleave explicit reasoning traces with action steps | +34% ALFWorld / +10% WebShop vs. pure RL; the foundational lever for virtually all agent task types |
| **Chain-of-Thought (CoT)**: force step-by-step reasoning before answering | Consistent improvement on math, logic, and multi-step QA; cost is prompt tokens only |

> ReAct structures how an agent thinks and acts; CoT structures how it reasons — together they cover 80% of reasoning quality improvements across agent benchmarks.

---

### 02 Memory

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Workflow Memory (AWM)**: induce reusable routines from past tasks | Mind2Web +24.6% / WebArena +51.1% relative improvement; eliminates redundant exploration on repeated task types |
| **In-context working memory**: structured state tracking within the active context window | Enables multi-step task coherence without external storage; covers 80% of short-horizon memory needs |

> Workflow Memory handles long-term reuse; working memory handles within-episode state — together they cover 80% of agent memory requirements.

---

### 03 Tool Use

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Structured function calling** (JSON Schema / typed interfaces) | Stable, parseable tool invocation; eliminates free-text parsing failures that cause the majority of tool use errors |
| **Tool routing / selection**: matching task class to the right tool | Correct tool selection determines whether the task is solvable at all; wrong tool = guaranteed failure |

> Reliable invocation + correct selection together cover 80% of tool use engineering failures.

---

### 04 Planning

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Hierarchical task decomposition**: goal → subgoals → actions | Prevents context overload and enables parallel subgoal execution; the dominant pattern in long-horizon planning papers |
| **Plan-then-execute with replanning**: generate plan, execute, detect failure, revise | Handles the majority of task failures that come from unexpected intermediate states |

> Decomposition reduces complexity; replanning handles reality deviation — together they cover 80% of planning task success.

---

### 05 Multi-Agent

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Role specialization**: each agent has a clearly bounded domain / skill | Reduces hallucination cascades; MetaGPT's SOP validates that role clarity is the single largest quality lever in multi-agent systems |
| **Structured communication protocol**: typed message passing between agents | Prevents error amplification across agent chains; unstructured communication is the root cause of most multi-agent coordination failures |

> Role clarity + structured messaging cover 80% of multi-agent coordination quality problems.

---

### 06 Code Agents

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Agent-Computer Interface (ACI) design**: build agent-specific interfaces, not human-facing UIs | ACI design determines the performance ceiling; SWE-bench 12.5% (SOTA) / HumanEvalFix 87.7% validate this as the #1 lever |
| **Iterative feedback loop**: run → observe output → diagnose → fix | Covers ~80% of coding errors that are detectable from execution output alone |

> ACI defines what the agent can perceive and do; iterative feedback covers most fixable errors — together they set and approach the performance ceiling.

---

### 07 RAG / Retrieval

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Dense vector retrieval** (embedding-based semantic search) | Outperforms keyword search on paraphrase and semantic variation; the default retrieval backbone for most RAG agent systems |
| **Self-RAG (adaptive retrieval)**: retrieve only when needed, with self-assessment of retrieval quality | Outperforms ChatGPT on QA/reasoning/factuality; avoids over-retrieval noise that degrades performance |

> Dense retrieval provides quality; adaptive triggering prevents noise — together they cover 80% of RAG agent performance gains.

---

### 08 Agent Evaluation

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Real-world task benchmarks**: actual browser / OS / code environments, not synthetic tasks | Reveals true capability gaps; OSWorld's 72% human vs. 12% AI gap would be invisible in synthetic benchmarks |
| **Multi-metric evaluation**: success rate + step efficiency + safety violations | Single-metric (success only) masks 80% of failure mode diversity |

> Real environments reveal true gaps; multi-metric scoring captures failure diversity — together they cover 80% of meaningful evaluation signal.

---

### 09 Agent Safety

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Sandboxed execution environment**: isolate agent actions from production systems | Prevents catastrophic irreversible actions; the minimum viable safety boundary for any deployed agent |
| **Output filtering + action whitelisting**: constrain the action space to pre-approved operations | Blocks most harmful outputs without requiring the agent to reason about safety |

> Sandbox contains blast radius; whitelisting constrains the attack surface — together they cover 80% of practical agent safety requirements, though no universal solution yet delivers both safety and high performance.

---

### 10 Embodied AI

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Closed-loop perception-action** (observe → act → observe with feedback) | The fundamental prerequisite for physical task success; open-loop execution fails on any real-world physical variance |
| **Skill primitive library** (Voyager paradigm): reusable action building blocks | 3.3× items / 15.3× milestones; skills learned in one context transfer to novel tasks — compounds capability |

> Closed-loop feedback handles reality; skill libraries compound capability — together they cover 80% of embodied agent performance.

---

### 11 Agent Architecture

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **LLM-as-controller + modular tools**: LLM for reasoning, separate modules for memory / planning / tools | The dominant architecture pattern across most agent systems; separation enables independent module improvement |
| **Context management strategy**: what to keep, summarize, or offload to external storage | Context window management is the hidden bottleneck; failure here causes most long-task coherence failures |

> Modular architecture enables flexibility; context strategy enables coherence — together they cover 80% of agent architecture design decisions.

---

### 12 Self-Improvement

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Structured self-reflection**: identify specific error type before proposing a fix | Random retry fails; structured diagnosis of "why it failed" drives most iterative refinement gains |
| **Feedback-driven iterative refinement**: use execution output / critic signal as refinement input | The core loop across self-improving systems; covers coding, writing, reasoning, and planning tasks |

> Diagnosis before fix + execution feedback as signal — together they cover 80% of self-improvement gains across agent types.

---

### 13 Roleplay

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Persona consistency via system prompt**: define character knowledge, tone, and boundaries in the system prompt | The single most effective lever for character consistency; covers 80% of roleplay quality issues |
| **Knowledge boundary enforcement**: character only knows what they would know in-world | Prevents immersion-breaking anachronisms and hallucinations; the second-largest failure mode in roleplay agents |

> Persona definition + knowledge boundary — together they cover 80% of roleplay character quality problems.

---

### 14 Long-Horizon Tasks

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Subgoal decomposition with explicit checkpoints**: break long task into verifiable milestones | Most long-horizon failures occur at subgoal boundaries; explicit checkpoints catch failures before they propagate |
| **State persistence and recovery**: save task state at each checkpoint, resume from last success | Prevents restarting 100-step tasks from scratch; covers 80% of long-horizon reliability requirements |

> Subgoal decomposition + checkpoint recovery — together they cover 80% of long-horizon task engineering challenges.

---

[中文说明](README.zh-CN.md) | [Back to main](../README.md)
