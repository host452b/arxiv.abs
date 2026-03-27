# arxiv.prompt — AI/LLM Prompt Engineering

4,780 curated arXiv paper abstracts on AI/LLM Prompt Engineering (2023–2026), with a structured summary of 50 core techniques.

## Core Techniques Summary

- [**English** — 50 Core Techniques](prompt_ai.md)
- [**中文** — 50 项核心技巧总结](prompt_ai.zh-CN.md)

## Abstracts by Year

| Year | Papers | Directory |
|------|--------|-----------|
| 2023 | 1,085 | [2023/](2023/) |
| 2024 | 1,478 | [2024/](2024/) |
| 2025 | 1,817 | [2025/](2025/) |
| 2026 | 400 | [2026/](2026/) |

Each year folder contains:
- `arxiv-results-YYYY.json` — full metadata (title, authors, abstract, categories, citations)
- `abstracts/` — individual `.txt` files (80 chars/line)

---

## Best Practices by Section (80/20 Pareto)

> **Pareto Principle:** In each prompting domain, 20% of key techniques account for 80% of measurable LLM performance gains. Each lever below reflects the highest-frequency consensus from the 4,780 prompt engineering papers.

### I. Reasoning & CoT (#1–6)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Chain-of-Thought (CoT)**: add "Let's think step by step" or demonstrate reasoning traces | The most cited prompting technique in the literature; consistent gains on math, logic, and multi-step QA with zero training cost |
| **ReAct**: interleave reasoning traces with action steps (Thought → Action → Observation) | Extends CoT to agentic settings; +34% ALFWorld / +10% WebShop vs. pure RL; covers 80% of reasoning-in-action use cases |

> CoT handles reasoning quality; ReAct extends it to action — together they cover 80% of reasoning prompt engineering gains.

---

### II. Examples & In-Context Learning (#7–11)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Diverse exemplar selection**: choose demonstrations that are semantically varied and representative of the task distribution | Example quality (not quantity) determines ICL performance; 3 well-chosen examples often outperform 10 random ones |
| **Self-consistency**: sample multiple reasoning paths, take the majority vote | Improves accuracy 5–15% over single-path CoT on reasoning tasks; requires no additional training, only inference compute |

> Exemplar quality + self-consistency cover 80% of ICL performance optimization.

---

### III. Design & Formatting (#12–16)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Role specification** ("You are an expert X..."): assigns a persona and knowledge domain | Consistent improvement in domain-specific tasks; one of the highest-ROI single-line additions to any prompt |
| **Structured output format** (JSON / XML / markdown schema): specify the exact output structure | Eliminates post-processing failures; the single most impactful formatting choice for programmatic LLM use |

> Role specification focuses the LLM; structured output makes it usable — together they cover 80% of prompt design quality.

---

### IV. Orchestration & Workflow (#17–22)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Prompt chaining**: break complex tasks into sequential prompts, each building on previous output | Avoids single-prompt context overload; covers 80% of multi-step task orchestration needs |
| **Multi-agent delegation**: route subtasks to specialist agents with bounded domains | Reduces hallucination and increases quality for tasks with distinct skill requirements; MetaGPT / AutoGen pattern |

> Chaining handles sequential complexity; multi-agent handles skill diversity — together they cover 80% of complex LLM workflow orchestration.

---

### V. Optimization & Compression (#23–28)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Automatic Prompt Optimization (APO / OPRO)**: use LLM feedback to iteratively improve prompt wording | Outperforms human-written prompts on most benchmarks; the "compile your prompt" paradigm |
| **Prompt compression**: remove redundant tokens while preserving semantic content (LLMLingua style) | 3–20× token reduction with <5% performance loss; directly reduces cost and latency for deployed systems |

> APO maximizes quality; compression maximizes efficiency — together they cover 80% of prompt optimization engineering.

---

### VI. Quality & Robustness (#29–33)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **LLM-as-Judge**: use a strong LLM (GPT-4 / Claude) to evaluate outputs against a rubric | Correlates 80%+ with human judgment at 1/100th the cost; the standard scalable evaluation method |
| **Sensitivity testing**: test prompt variants (paraphrase, reorder, change examples) to measure output stability | Unstable prompts fail silently in production; sensitivity testing reveals fragility before deployment |

> LLM-as-Judge measures quality; sensitivity testing measures reliability — together they cover 80% of prompt quality assurance needs.

---

### VII. Defense & Protection (#34–41)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Spotlighting**: clearly delimit user-provided content (XML tags, special tokens) to separate from system instructions | The highest-efficacy single defensive technique; makes injection structurally difficult by marking trust boundaries |
| **Input sanitization + allowlist validation**: filter or escape dangerous patterns; only permit expected input schemas | Blocks 80% of prompt injection attacks at the input boundary before they reach the LLM |

> Spotlighting defends instruction integrity; input sanitization defends at the boundary — together they cover 80% of prompt injection defense.

---

### VIII. Attacks & Security Research (#42–50)

| Critical Lever (20%) | Impact Covered (80%) |
|----------------------|----------------------|
| **Role-play / persona jailbreak**: instruct the model to "act as" a character without safety constraints | The most prevalent jailbreak technique; responsible for the majority of safety filter bypasses documented in the literature |
| **Indirect prompt injection**: embed malicious instructions in external content (web pages, documents, emails) that the LLM processes | The highest-severity attack vector for deployed agents; bypasses all direct-input defenses by poisoning the context |

> Persona jailbreak is the dominant direct attack; indirect injection is the dominant agentic attack — understanding both covers 80% of the LLM attack surface.

---

[Back to main README](../README.md) | [中文说明](README.zh-CN.md)

---

## Paradigm Shifts / 范式转移 (Kuhn)

| Old Paradigm | Trigger Event | New Paradigm |
|---|---|---|
| **Rule-based NLP** — hand-coded templates and grammars | GPT-3 / few-shot learning (2020): in-context learning | **Prompt-based generalization** — no fine-tuning needed for new tasks |
| **Fine-tune per task** — labeled datasets required for every task | InstructGPT / RLHF (2022): alignment training | **Instruction-following base models** — one model handles any task via prompting |
| **Human-written fixed prompts** — artisanal prompt engineering | APO / OPRO (2023): LLM-evaluates-LLM optimization | **Automated prompt optimization** — treat prompt-writing as a compile step |
| **Static prompt templates** — frozen context window | RAG + tool use (2023+): external knowledge access | **Dynamic retrieval-augmented prompts** — grounded, always-current context |

**已被推翻的认知误区 / Overturned Beliefs:**
- ✗ "更长的提示词 = 更好的结果" → 质量 > 数量；聚焦明确的提示胜过冗长堆砌
- ✗ "同一个提示适用于所有模型" → 不同模型需要模型专属优化
- ✗ "少样本 = 多给例子" → 3个精心挑选的例子胜过10个随机例子
- ✗ "系统提示绝对有效" → 越狱和提示注入可绕过系统提示
- ✗ "CoT总能提升性能" → 简单任务上CoT引入冗余推理，反而降低准确率

