# arxiv.agent-harness

An arXiv abstract collection covering the full lifecycle of **LLM-based agent systems**:
frameworks, orchestration, planning, tool use, memory, multi-agent coordination,
evaluation, safety, code agents, browser/GUI agents, and production reliability.

- **Time range**: 2020–2026 (AI-agent era focus)
- **Total unique papers**: 2,177
- **Search files**: 42 topic-based searches
- **Year distribution**: 2020(49) · 2021(55) · 2022(80) · 2023(198) · 2024(482) · 2025(949) · 2026(339)

---

## Search Topics (42 Searches)

| ID | Topic | File | Superseded Theory / Established Fallacy |
|---|---|---|---|
| 01 | Agent Framework & Orchestration | `01-agent-framework.json` | "A single monolithic LLM can handle all agent tasks" → Multi-agent specialization, routing, and orchestration are required for complex tasks. |
| 02 | AutoGen / LangChain / CrewAI | `02-autogen-langchain.json` | "Framework abstractions always reduce complexity" → LangChain/LangGraph abstractions add debugging difficulty; raw LLM API calls are often more debuggable. |
| 03 | Agentic Workflow & Pipeline | `03-agentic-workflow.json` | "Agent workflows should maximize autonomy" → Fully autonomous agents fail silently and compound errors; human-in-the-loop checkpoints are essential. |
| 04 | LLM Agent (general) | `04-llm-agent.json` | "LLM agents are reliable for production use out of the box" → Agents fail at rates of 20–60% on real-world tasks; evaluation harnesses and retry loops are mandatory. |
| 05 | ReAct: Reasoning + Action | `05-react-agent.json` | "Longer ReAct chains always improve reasoning" → Long chains compound errors; self-verification loops and tool output validation are required. |
| 06 | Chain-of-Thought + Tool Use | `06-chain-of-thought-act.json` | "Chain-of-thought always improves agent decisions" → CoT can introduce verbose irrelevant reasoning; step-level verification is needed. |
| 07 | Tree / Graph of Thought | `07-tree-of-thought.json` | "Tree of Thought is always better than linear CoT" → ToT's computational cost is prohibitive for most tasks; linear CoT with backtracking is usually sufficient. |
| 08 | Agent Planning & Task Planning | `08-agent-planning.json` | "Agents can plan effectively without world model grounding" → Ungrounded plans hallucinate feasibility; execution feedback must update the plan iteratively. |
| 09 | Self-Reflection & Self-Critique | `09-self-reflection.json` | "Agents can self-diagnose all errors through reflection" → Self-reflection has systematic blind spots; external verification agents are more reliable for certain failure types. |
| 10 | Agent Reasoning & Decision | `10-agent-reasoning.json` | "Larger models are always better reasoners" → Reasoning quality depends on problem framing, not just scale; structured output constraints matter more at task level. |
| 11 | Tool Use with LLM | `11-tool-use-llm.json` | "LLMs reliably use tools without explicit examples" → Without few-shot tool use examples, error rates in parameter formatting and tool selection are high. |
| 12 | Function Calling / API Calling | `12-function-calling.json` | "Function calling eliminates hallucinated API calls" → Hallucinated parameter values and wrong function selection remain common failure modes. |
| 13 | Tool Selection & Learning | `13-tool-selection.json` | "More tools = better agent performance" → Tool overload degrades selection accuracy; tool pruning and dynamic tool retrieval improve performance. |
| 14 | Agent Memory & Episodic Memory | `14-agent-memory.json` | "Longer context windows solve agent memory" → Long contexts suffer recall degradation at middle positions; explicit memory management outperforms relying on context length. |
| 15 | Long Context for Agents | `15-long-context.json` | "LLMs reliably attend to all parts of long contexts" → 'Lost in the middle' effect: retrieval accuracy drops sharply for information in the middle of long contexts. |
| 16 | Memory Module & Agent State | `16-memory-module.json` | "Vector-store RAG is always the right memory architecture" → Episodic, semantic, and working memory require different storage strategies; one-size-fits-all RAG underperforms. |
| 17 | Multi-Agent with LLM | `17-multi-agent-llm.json` | "Multi-agent systems converge to correct answers" → Without consensus mechanisms, multi-agent debates can amplify initial errors rather than correct them. |
| 18 | Agent Communication & Coordination | `18-agent-communication.json` | "Agents communicate reliably via natural language" → Structured message formats (JSON schemas) significantly reduce miscommunication between agents. |
| 19 | Role-Playing Agent & Persona | `19-role-playing-agent.json` | "Role-playing eliminates model behavioral constraints" → Role-playing is a recognized jailbreak vector; system-level constitutional constraints are required. |
| 20 | Society of Agents | `20-society-agents.json` | "Larger agent societies produce better outcomes" → Society of Mind experiments show diminishing returns and coordination overhead beyond ~5 agents. |
| 21 | Agent Benchmark & Evaluation | `21-agent-benchmark.json` | "High benchmark scores predict real-world agent performance" → Benchmark leakage and task familiarity inflate scores; novel task generalization is still poor. |
| 22 | Agent Capability & Performance | `22-agent-capability.json` | "Agent capabilities transfer across domains" → Domain-specific tool knowledge does not generalize; agents need domain-specific grounding. |
| 23 | Agentic Evaluation (autonomous) | `23-agentic-eval.json` | "Agent evaluation can rely on LLM-as-judge alone" → LLM judges have systematic biases (position, verbosity, self-preference); ensemble judging is needed. |
| 24 | Agent Safety & Alignment | `24-agent-safety.json` | "Safety guardrails make agents safe" → Guardrails are bypassable; safety must be embedded in training, architecture, and human oversight. |
| 25 | Agent Guardrails & Constraints | `25-agent-guardrail.json` | "Keyword-based guardrails prevent harmful outputs" → Semantic equivalence and paraphrasing easily bypass lexical guardrails; semantic safety classifiers are needed. |
| 26 | Red-Teaming Agents | `26-red-teaming-agent.json` | "Red-teaming with a fixed prompt set is comprehensive" → Automated red-teaming (e.g., PAIR, tree-based attacks) explores adversarial space far more thoroughly. |
| 27 | Agent Sandboxing & Isolation | `27-agent-sandbox.json` | "Sandboxing agents prevents all side effects" → Network-based and social engineering side channels can escape code-level sandboxes. |
| 28 | Code Agent & Coding Agent | `28-code-agent.json` | "Code agents can autonomously maintain large codebases" → Agents lose coherence beyond ~1000 lines of relevant context; repo-level agents require explicit chunking. |
| 29 | SWE-Agent & Software Eng. Agent | `29-swe-agent.json` | "SWE-bench performance predicts production software engineering ability" → SWE-bench has distribution leakage and limited task diversity; real-world SE is far more open-ended. |
| 30 | Autonomous Coding & AI Programmer | `30-autonomous-coding.json` | "Autonomous coding agents reduce bugs" → Agents introduce new bug patterns (hallucinated APIs, subtle logic errors) while eliminating others. |
| 31 | Repository / Codebase Agent | `31-repo-agent.json` | "Repo-level agents understand the full codebase" → Context window limits force chunking strategies that lose cross-file dependencies. |
| 32 | Web Agent & Browser Agent | `32-web-agent.json` | "Web agents work reliably on dynamic pages" → JavaScript-heavy SPAs and anti-bot CAPTCHAs remain major practical barriers. |
| 33 | Computer Use & GUI Agent | `33-computer-use.json` | "Computer-use agents can replace desktop automation scripts" → Reliability and latency of vision-based computer use are still far below scripted RPA for deterministic tasks. |
| 34 | Web Navigation & Browsing | `34-web-navigation.json` | "DOM-based navigation is more reliable than vision-based" → DOM injection changes frequently; a hybrid vision + accessibility tree approach is most robust. |
| 35 | RAG + Agent | `35-rag-agent.json` | "RAG eliminates hallucination" → RAG reduces but does not eliminate hallucination; retrieval quality determines output quality. |
| 36 | Knowledge Retrieval Agent | `36-knowledge-agent.json` | "Knowledge graphs + LLMs = factual accuracy" → Knowledge graph coverage is incomplete; LLMs still hallucinate facts not covered by the KG. |
| 37 | Long-Horizon Agent & Tasks | `37-long-horizon.json` | "LLMs can maintain coherent plans over 100+ steps" → Long-horizon task success rates drop dramatically; checkpointing and replanning are required. |
| 38 | Agent Reliability & Robustness | `38-agent-reliability.json` | "Retry loops solve agent reliability" → Retries on the same failed strategy often repeat the same error; retry-with-strategy-switch is needed. |
| 39 | Agent Testing & Debugging | `39-agent-testing.json` | "Traditional software testing applies to agents" → Agent testing requires non-determinism handling, trajectory evaluation, and emergent behavior testing. |
| 40 | Human-in-the-Loop Agent | `40-human-loop-agent.json` | "Human review is only needed for high-stakes decisions" → Human oversight of intermediate agent steps dramatically improves final outcome quality. |
| 41 | Agent Monitoring & Observability | `41-agent-monitoring.json` | "Logging agent outputs is sufficient observability" → Agent observability requires full execution trace (tool calls, intermediate states, branching decisions). |
| 42 | Evaluation Harness & Agent Harness | `42-agent-eval-harness.json` | "Leaderboard rankings are stable proxies for agent quality" → Leaderboard gaming and benchmark contamination make rankings unreliable; domain-specific eval is needed. |

---

## Category Analysis (12 Clusters)

### A01 · Agent Frameworks & Orchestration — 139 papers

Core infrastructure for building agent systems.

| Sub-topic | Count | 80/20 Core Papers |
|-----------|-------|-------------------|
| Framework design (LangChain, AutoGen, CrewAI) | ~55 | multi-framework comparisons, design patterns |
| Orchestration & pipeline | ~45 | task decomposition, agent chaining |
| General agentic workflow | ~39 | pipeline automation, agent-as-service |

**80/20**: ~30 papers on framework design and LLM orchestration account for most
practical knowledge. Focus on architectural comparisons and failure mode studies.

---

### A02 · Planning & Reasoning — 104 papers

How agents plan multi-step tasks and reason before acting.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| ReAct (Reason + Act) | ~35 | original ReAct paper + extensions |
| Tree/Graph of Thought | ~28 | ToT, GoT, breadth-first planning |
| Self-reflection & critique | ~25 | Reflexion, iterative refinement |
| Task planning | ~16 | hierarchical planning, sub-goal generation |

**80/20**: ReAct and Tree-of-Thought variants form the dominant paradigm.
~25 papers cover the essential planning primitives used in production agents.

---

### A03 · Tool Use & Function Calling — 77 papers

Grounding agents in real-world actions via tool invocation.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Tool use with LLMs | ~35 | Toolformer, ToolBench, API grounding |
| Function calling | ~25 | OpenAI-style function calling, schema design |
| Tool selection & learning | ~17 | which tool to use and when |

**80/20**: ~15 papers on function-calling paradigm + tool selection strategies
cover the practical implementation for production systems.

---

### A04 · Memory & Context Management — 32 papers

Persistent memory beyond the context window.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Agent memory systems | ~18 | MemGPT, episodic + semantic memory |
| Long-context agents | ~9 | RAG vs long context, retrieval-augmented agents |
| Memory modules | ~5 | external memory stores, vector DB integration |

**80/20**: MemGPT-style memory augmentation + retrieval strategies (~10 papers)
form the practical foundation.

---

### A05 · Multi-Agent Systems — 412 papers ⭐ (largest cluster)

Coordination, communication, and emergent behavior among multiple LLM agents.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| General multi-agent LLM | ~180 | coordination protocols, agent societies |
| Agent communication & negotiation | ~100 | message passing, dialogue protocols |
| Role-playing & persona-based | ~70 | specialized roles, agent differentiation |
| Society of agents | ~62 | emergent behavior, agent ecosystems |

**80/20**: ~80 papers on multi-agent communication protocols and role-based
decomposition cover the dominant research patterns. ChatDev, MetaGPT, and similar
society-level papers are most cited.

---

### A06 · Agent Benchmarks & Evaluation — 66 papers

How to measure what agents can and cannot do.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Agent benchmark suites | ~30 | WebArena, AgentBench, GAIA, SWE-bench |
| Capability evaluation | ~22 | task completion rate, error analysis |
| Autonomous agent benchmarks | ~14 | agentic vs static eval |

**80/20**: ~15 widely-cited benchmark papers (SWE-bench, WebArena, AgentBench)
define the evaluation landscape.

---

### A07 · Agent Safety & Guardrails — 18 papers

Preventing harmful or unintended agent actions.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Agent safety / alignment | ~10 | specification gaming, goal misgeneralization |
| Guardrails & constraints | ~5 | hard constraints, action filtering |
| Sandboxing & isolation | ~3 | container-level isolation |

**80/20**: A small but critical cluster. ~8 core papers on agent-specific safety
(distinct from general LLM safety) are foundational.

---

### A08 · Code & Software Engineering Agents — 109 papers

AI agents that write, debug, and modify code.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| General code agents | ~45 | CodeAct, OpenDevin, Aider, Cursor |
| SWE-agent for bug fixing | ~35 | GitHub issue resolution, PR generation |
| Autonomous coding | ~20 | AI programmer, scaffold-free coding |
| Repo/codebase agents | ~9 | whole-repo understanding, multi-file edits |

**80/20**: SWE-bench + SWE-agent + 10 code-agent framework papers cover ~80%
of the practical knowledge for building coding agents.

---

### A09 · Web & Computer-Use Agents — 200 papers

Agents that navigate browsers, GUIs, and web environments.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Web agent & browser agent | ~80 | WebGPT, WebAgent, Mind2Web |
| Computer use & GUI agent | ~70 | Claude Computer Use, AppAgent, UI grounding |
| Web navigation | ~50 | DOM manipulation, screenshot-based navigation |

**80/20**: ~40 papers on GUI/web grounding and navigation strategies capture
the core techniques. Computer use papers accelerated rapidly in 2024–2025.

---

### A10 · RAG & Knowledge Agents — 590 papers ⭐ (2nd largest)

Retrieval-augmented generation as a core agent capability.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| RAG + agent integration | ~280 | agentic RAG, iterative retrieval |
| Knowledge retrieval agents | ~180 | KG integration, structured knowledge |
| Retrieval strategies | ~130 | dense retrieval, re-ranking |

**80/20**: The original RAG paper + ~50 agentic RAG variants cover the essential
patterns. Iterative/self-ask retrieval is the current frontier.

---

### A11 · Long-Horizon & Reliability — 94 papers

Sustaining correct behavior over extended tasks.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Long-horizon tasks | ~50 | multi-day tasks, persistent state |
| Agent reliability & robustness | ~25 | error recovery, retry strategies |
| Agent testing & debugging | ~19 | automated testing, trace analysis |

**80/20**: ~20 papers on long-horizon task decomposition and failure recovery
cover the core reliability engineering for agents.

---

### A12 · Human-AI Collaboration & Observability — 28 papers

Keeping humans informed and in control.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Human-in-the-loop | ~15 | approval workflows, HITL patterns |
| Agent monitoring & observability | ~8 | trace logging, anomaly detection |
| Evaluation harness | ~5 | CI/CD for agents, regression testing |

**80/20**: ~10 papers on HITL design patterns and agent observability are
foundational for production deployment.

---

## Cross-Cutting Findings

1. **2024–2025 acceleration**: 68% of all papers published in these two years,
   reflecting the explosion of agent-focused research after GPT-4 and Claude 3.

2. **Multi-agent dominance**: A05 (412 papers) and A10/RAG (590) are the two
   largest clusters, indicating that multi-agent coordination and retrieval
   augmentation are the central research themes.

3. **Software agents as a flagship benchmark**: A08 code agents have SWE-bench
   as a unifying evaluation standard — the most impactful agent benchmark to date.

4. **Safety remains underdeveloped**: A07 (18 papers) is disproportionately small
   relative to the agent deployment footprint — a key research gap.

5. **GUI/computer-use emerging fast**: A09 grew 5× from 2023 to 2025, driven by
   Claude Computer Use, GPT-4V, and open-source GUI agent frameworks.

---

## arXiv Category Breakdown

| Category | Papers | Focus Area |
|----------|--------|-----------|
| cs.AI | 480 | Artificial Intelligence (general agent architectures) |
| cs.CL | 465 | Computation & Language (LLM-grounded agents) |
| cs.LG | 194 | Machine Learning (learning-based agent components) |
| cs.SE | 190 | Software Engineering (coding agents, SWE-bench) |
| cs.CR | 114 | Cryptography & Security (agent safety, red-teaming) |
| cs.CV | 84 | Computer Vision (GUI/visual agents) |

---

[中文说明](README.zh-CN.md) | [知识文档](agent-harness.md) | [返回主目录](../README.md)

---

## Paradigm Shifts / 范式转移 (Kuhn)

```
OLD PARADIGM                    Trigger Event                   NEW PARADIGM
─────────────────────          ─────────────────────          ─────────────────────
Single monolithic LLM           GPT-4 + tool calling (2023)   Multi-agent orchestration
  │ one model for everything        │ function calling API          │ specialist agents + router
  └──────────────────────────────── ┘                             │
                                                                   │
Static prompt → output          ReAct paper (2022)            Thought-Action-Observation loops
  │ input → response                │ interleaved reasoning/action  │ agents iterate on environment
  └──────────────────────────────────┘                             │
                                                                   │
Human-written test scripts      Eval harness research (2023+) LLM-as-Judge + auto eval
  │ humans evaluate outputs         │ MT-Bench, HELM, AgentBench    │ automated trajectory evaluation
  └──────────────────────────────────┘                             │
                                                                   │
"Agents are reliable enough"    SWE-bench, ToolBench (2023)   Reliability-first engineering
  │ deploy and hope                  │ 20–60% task success rates     │ retry loops, checkpointing
  └──────────────────────────────────┘
```

**已被推翻的认知误区 / Overturned Beliefs:**
- ✗ "更长的ReAct链总能提升推理" → 长链会放大错误；需要工具输出验证和回退策略
- ✗ "RAG消除幻觉" → RAG将问题转移到检索质量；检索差则输出差
- ✗ "沙盒环境防止所有副作用" → 网络和社会工程侧信道可绕过代码层沙盒
- ✗ "高基准分数预测真实世界性能" → 基准污染和泄漏使排行榜分数不可靠

