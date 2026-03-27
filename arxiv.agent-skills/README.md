# arxiv.agent-skills — AI Agent Skills: Full Technical Landscape

**2,606 arXiv abstracts** from 14 targeted searches in the CS category, systematically covering the core skill techniques in AI Agent research.

**Core question:** Which skill combinations deliver the maximum task capability gain at minimum engineering cost?

## Search Topics

| # | Skill Category | Keywords | Papers | File | Superseded Theory / Established Fallacy |
|---|---|---|---|---|---|
| 01 | Reasoning | chain of thought / tree of thought / ReAct / self reflection | 200 | [01-reasoning.json](search-results/01-reasoning.json) | "LLMs cannot do formal reasoning" → Chain-of-thought and scratchpad prompting enable multi-step logical and mathematical reasoning beyond what was thought possible at scale. |
| 02 | Memory | agent memory / episodic memory / working memory / memory augmented | 200 | [02-memory.json](search-results/02-memory.json) | "Transformers cannot have persistent memory" → External memory stores (RAG, episodic memory modules) give LLM agents indefinite effective memory beyond context window limits. |
| 03 | Tool Use | tool use / function calling / tool augmented / API agent / tool learning | 200 | [03-tool-use.json](search-results/03-tool-use.json) | "LLMs cannot reliably use external tools" → ReAct and function-calling have made reliable tool use mainstream; the original 'LLMs can only generate text' assumption is obsolete. |
| 04 | Planning | task planning / task decomposition / hierarchical planning / goal decomposition | 200 | [04-planning.json](search-results/04-planning.json) | "LLMs cannot plan multi-step tasks" → LLM-based planners (HuggingGPT, ToT) demonstrate multi-step task decomposition; the claim they 'cannot plan' is too strong. |
| 05 | Multi-Agent | multi agent / multiagent cooperation / agent coordination / agent collaboration | 200 | [05-multiagent.json](search-results/05-multiagent.json) | "Multi-agent systems always outperform single agents" → Without coordination protocols and consensus mechanisms, multi-agent debates can amplify errors rather than correct them. |
| 06 | Code Agents | code agent / software agent / coding agent / SWE agent / autonomous coding | 200 | [06-code-agents.json](search-results/06-code-agents.json) | "Code generation requires specialized training on code" → General-purpose LLMs generalize to code through in-context learning; code-specific training provides incremental improvement. |
| 07 | RAG / Retrieval | retrieval augmented agent / knowledge retrieval agent / RAG agent | 200 | [07-rag-retrieval.json](search-results/07-rag-retrieval.json) | "RAG eliminates LLM hallucination" → RAG shifts the problem to retrieval quality; 'garbage in, garbage out' — bad retrieval produces confidently wrong augmented output. |
| 08 | Agent Evaluation | agent benchmark / agent evaluation / LLM agent benchmark | 200 | [08-agent-eval.json](search-results/08-agent-eval.json) | "Human evaluation is the gold standard for agents" → Human evaluation is expensive, inconsistent, and slow; calibrated LLM-as-judge achieves comparable correlation at scale. |
| 09 | Agent Safety | agent safety / agent alignment / agent oversight / LLM agent attack | 200 | [09-agent-safety.json](search-results/09-agent-safety.json) | "Safety-trained agents are safe in all contexts" → Safety is brittle under distribution shift; agents safe in training environments can exhibit unsafe behavior in novel contexts. |
| 10 | Embodied AI | embodied agent / embodied AI / grounded agent / physical agent | 200 | [10-embodied.json](search-results/10-embodied.json) | "Robot intelligence requires hand-engineered control loops" → Foundation models (RT-2, π0) transfer internet-scale knowledge to robotic manipulation with minimal task-specific engineering. |
| 11 | Agent Architecture | LLM agent / autonomous agent architecture / agentic framework | 200 | [11-agent-arch.json](search-results/11-agent-arch.json) | "Transformer architecture is sufficient for AGI" → Memory bandwidth, energy efficiency, and compositional generalization challenges motivate architectural innovation beyond pure transformers. |
| 12 | Self-Improvement | self improvement agent / self refinement / self correction / iterative refinement | 200 | [12-self-improve.json](search-results/12-self-improve.json) | "Self-improvement leads to intelligence explosion" → Practical self-improvement is constrained by search costs and objective specification; theoretical explosion scenarios ignore these. |
| 13 | Roleplay | role playing agent / persona agent / character simulation / roleplay LLM | 116 | [13-roleplay.json](search-results/13-roleplay.json) | "Role-playing is benign and just a creative feature" → Role-playing is a documented jailbreak vector; constitutional constraints must persist through persona adoption. |
| 14 | Long-Horizon | long horizon agent / autonomous agent task / web agent / computer agent | 200 | [14-long-horizon.json](search-results/14-long-horizon.json) | "Long-horizon agents just need more context" → Context window scaling doesn't solve coherence decay; planning, state tracking, and re-planning are separate architectural requirements. |

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

| Old Paradigm | Trigger Event | New Paradigm |
|---|---|---|
| **LLMs are text generators only** — text in, text out | ReAct / tool calling (2022): thought-action-observation | **Tool-using reasoning agents** — agents act in live environments |
| **Specialized per-task training** — fine-tune a separate model per skill | GPT-4 generalization (2023): in-context skill learning | **General agents with skill transfer** — one agent, many domains |
| **Human-in-the-loop as bottleneck** — humans slow everything down | HITL research (2023+): approval gates improve quality | **Human-in-the-loop as quality multiplier** — oversight leads to better outcomes |

**已被推翻的认知误区 / Overturned Beliefs:**
- ✗ "LLM无法进行形式推理" → CoT和草稿本提示使多步逻辑和数学推理成为可能
- ✗ "Transformer无法拥有持久记忆" → 外部记忆存储（RAG、情景记忆模块）赋予LLM超越上下文窗口的有效记忆
- ✗ "多智能体系统总是优于单智能体" → 没有共识机制时，多智能体辩论会放大而非纠正初始错误
- ✗ "RAG消除LLM幻觉" → RAG将问题转移到检索质量；劣质检索产生错误的增强输出

