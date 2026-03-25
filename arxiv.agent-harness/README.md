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

| ID | Topic | File |
|----|-------|------|
| 01 | Agent Framework & Orchestration | `01-agent-framework.json` |
| 02 | AutoGen / LangChain / CrewAI | `02-autogen-langchain.json` |
| 03 | Agentic Workflow & Pipeline | `03-agentic-workflow.json` |
| 04 | LLM Agent (general) | `04-llm-agent.json` |
| 05 | ReAct: Reasoning + Action | `05-react-agent.json` |
| 06 | Chain-of-Thought + Tool Use | `06-chain-of-thought-act.json` |
| 07 | Tree / Graph of Thought | `07-tree-of-thought.json` |
| 08 | Agent Planning & Task Planning | `08-agent-planning.json` |
| 09 | Self-Reflection & Self-Critique | `09-self-reflection.json` |
| 10 | Agent Reasoning & Decision | `10-agent-reasoning.json` |
| 11 | Tool Use with LLM | `11-tool-use-llm.json` |
| 12 | Function Calling / API Calling | `12-function-calling.json` |
| 13 | Tool Selection & Learning | `13-tool-selection.json` |
| 14 | Agent Memory & Episodic Memory | `14-agent-memory.json` |
| 15 | Long Context for Agents | `15-long-context.json` |
| 16 | Memory Module & Agent State | `16-memory-module.json` |
| 17 | Multi-Agent with LLM | `17-multi-agent-llm.json` |
| 18 | Agent Communication & Coordination | `18-agent-communication.json` |
| 19 | Role-Playing Agent & Persona | `19-role-playing-agent.json` |
| 20 | Society of Agents | `20-society-agents.json` |
| 21 | Agent Benchmark & Evaluation | `21-agent-benchmark.json` |
| 22 | Agent Capability & Performance | `22-agent-capability.json` |
| 23 | Agentic Evaluation (autonomous) | `23-agentic-eval.json` |
| 24 | Agent Safety & Alignment | `24-agent-safety.json` |
| 25 | Agent Guardrails & Constraints | `25-agent-guardrail.json` |
| 26 | Red-Teaming Agents | `26-red-teaming-agent.json` |
| 27 | Agent Sandboxing & Isolation | `27-agent-sandbox.json` |
| 28 | Code Agent & Coding Agent | `28-code-agent.json` |
| 29 | SWE-Agent & Software Eng. Agent | `29-swe-agent.json` |
| 30 | Autonomous Coding & AI Programmer | `30-autonomous-coding.json` |
| 31 | Repository / Codebase Agent | `31-repo-agent.json` |
| 32 | Web Agent & Browser Agent | `32-web-agent.json` |
| 33 | Computer Use & GUI Agent | `33-computer-use.json` |
| 34 | Web Navigation & Browsing | `34-web-navigation.json` |
| 35 | RAG + Agent | `35-rag-agent.json` |
| 36 | Knowledge Retrieval Agent | `36-knowledge-agent.json` |
| 37 | Long-Horizon Agent & Tasks | `37-long-horizon.json` |
| 38 | Agent Reliability & Robustness | `38-agent-reliability.json` |
| 39 | Agent Testing & Debugging | `39-agent-testing.json` |
| 40 | Human-in-the-Loop Agent | `40-human-loop-agent.json` |
| 41 | Agent Monitoring & Observability | `41-agent-monitoring.json` |
| 42 | Evaluation Harness & Agent Harness | `42-agent-eval-harness.json` |

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
