# arxiv.anthropic-claude

An arXiv abstract collection focused on **Claude, Anthropic's research, and the
science behind safe, helpful AI**: Constitutional AI, RLHF/RLAIF, mechanistic
interpretability, alignment techniques, jailbreaking/adversarial attacks,
sycophancy, hallucination, scaling laws, and long-context capabilities.

- **Time range**: 2021–2026 (Claude-era focus)
- **Total unique papers**: 2,628
- **Search files**: 35 topic-based searches
- **Year distribution**: 2021(136) · 2022(123) · 2023(321) · 2024(718) · 2025(1058) · 2026(267)

---

## Search Topics (35 Searches)

| ID | Topic | File |
|----|-------|------|
| 01 | Claude Model Research | `01-claude-model.json` |
| 02 | Anthropic Research | `02-anthropic-research.json` |
| 03 | Claude Evaluation & Benchmarks | `03-claude-eval.json` |
| 04 | Claude Safety | `04-claude-safety.json` |
| 05 | Constitutional AI | `05-constitutional-ai.json` |
| 06 | RLHF | `06-rlhf.json` |
| 07 | RLAIF | `07-rlaif.json` |
| 08 | Reward Modeling | `08-reward-model.json` |
| 09 | Harmlessness | `09-harmlessness.json` |
| 10 | Helpful Harmless Honest (HHH) | `10-hhh-ai.json` |
| 11 | Preference Learning | `11-preference-learning.json` |
| 12 | Red-Teaming & Safety | `12-red-teaming-safety.json` |
| 13 | Mechanistic Interpretability | `13-mech-interp.json` |
| 14 | Superposition in Neural Nets | `14-superposition-nn.json` |
| 15 | Sparse Autoencoders | `15-sparse-autoencoder.json` |
| 16 | Activation Patching / Causal Tracing | `16-activation-patching.json` |
| 17 | Circuit-Level Interpretability | `17-circuit-interp.json` |
| 18 | Feature Interpretability | `18-feature-interp.json` |
| 19 | Attention Head Analysis | `19-attention-analysis.json` |
| 20 | Scaling Laws | `20-scaling-law.json` |
| 21 | Emergent Capabilities | `21-emergent-capability.json` |
| 22 | Capability Evaluation | `22-capability-eval.json` |
| 23 | AI Safety & Alignment Techniques | `23-ai-safety-align.json` |
| 24 | Jailbreaking | `24-jailbreak.json` |
| 25 | Alignment Training | `25-alignment-training.json` |
| 26 | Deceptive Alignment | `26-deceptive-alignment.json` |
| 27 | Sleeper Agents & Backdoors | `27-sleeper-agent.json` |
| 28 | Sycophancy | `28-sycophancy.json` |
| 29 | Honesty & Truthfulness | `29-honesty-llm.json` |
| 30 | Hallucination & Factuality | `30-hallucination.json` |
| 31 | Calibration & Uncertainty | `31-calibration-llm.json` |
| 32 | CoT Faithfulness & Reasoning | `32-cot-faithfulness.json` |
| 33 | Vision-Language Models | `33-vision-language.json` |
| 34 | Long Context LLM | `34-long-context-llm.json` |
| 35 | Context Window & Length | `35-context-window.json` |

---

## Category Analysis (12 Clusters)

### B01 · Claude & Anthropic Research — 85 papers

Direct research on Claude models and Anthropic publications.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Claude model papers | ~50 | Claude 1/2/3/3.5 technical reports, evals |
| Anthropic research | ~35 | Papers citing Anthropic, safety-focused research |

**80/20**: The handful of Claude technical reports and Anthropic safety papers
(~10) form the canonical reference set. All other papers cite or build on these.

---

### B02 · Constitutional AI & RLHF — 62 papers

The training methodology that defines Claude's behavior.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Constitutional AI | ~18 | CAI paper + derivatives, AI self-critique |
| RLHF | ~30 | InstructGPT, reward modeling, PPO variants |
| RLAIF | ~14 | AI feedback, self-improvement loops |

**80/20**: ~8 foundational papers (CAI, InstructGPT, Sparrow) define the
complete RLHF/CAI landscape. All post-2022 alignment training derives from these.

---

### B03 · Reward Modeling & Preference Learning — 89 papers

How to elicit and encode human preferences.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Reward modeling | ~40 | Reward model design, ensemble methods |
| Human preference learning | ~32 | Comparative feedback, pairwise ranking |
| HHH criteria | ~17 | Helpfulness + harmlessness + honesty tradeoffs |

**80/20**: ~20 papers on reward model design and preference dataset construction
cover the essential methodology for alignment training.

---

### B04 · Mechanistic Interpretability — 177 papers ⭐

Understanding the internal computations of transformers.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Mechanistic interpretability (general) | ~55 | Circuits, features, in-context learning |
| Superposition & sparse representation | ~45 | Toy models, polysemanticity |
| Sparse autoencoders (SAE) | ~32 | Feature decomposition, dictionary learning |
| Activation patching / causal tracing | ~25 | ROME, MEMIT, causal scrubbing |
| Circuit analysis | ~20 | Induction circuits, indirect object ID |

**80/20**: ~30 papers from Anthropic's interpretability team + key external
papers (ROME, Transformer Circuits) cover the essential methods and findings.

---

### B05 · Scaling Laws & Emergent Capabilities — 22 papers

How model behavior changes with compute and data.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Scaling laws | ~12 | Chinchilla, Kaplan, neural scaling laws |
| Emergent capabilities | ~10 | Emergent abilities paper, phase transitions |

**80/20**: ~5 seminal papers (Chinchilla scaling laws, emergent abilities survey)
are the core references for understanding capability vs. compute tradeoffs.

---

### B06 · Safety & Alignment Techniques — 163 papers ⭐

The technical toolkit for making AI safe.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Red-teaming | ~60 | Adversarial probing, jailbreak taxonomy |
| Jailbreaking attacks | ~45 | Prompt injection, GCG, DAN variants |
| AI safety alignment | ~35 | Goal stability, specification gaming |
| Deceptive alignment | ~15 | Sleeper agents, goal misgeneralization |
| Backdoor attacks | ~8 | Data poisoning, trigger injection |

**80/20**: ~40 red-teaming and jailbreak papers form the active research frontier.
Sleeper Agents (Anthropic) is the single most impactful deceptive alignment paper.

---

### B07 · Sycophancy & Honesty — 28 papers

Models that tell users what they want to hear vs. the truth.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Sycophancy detection & mitigation | ~18 | Measuring sycophancy, training interventions |
| Honesty & truthfulness | ~10 | TruthfulQA, calibration-based honesty |

**80/20**: ~8 papers covering Anthropic's sycophancy research, TruthfulQA, and
honesty training protocols define the field.

---

### B08 · Hallucination & Factuality — 199 papers ⭐

When models generate false or unsupported claims.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Hallucination detection | ~80 | Factuality benchmarks, detection methods |
| Factuality improvement | ~65 | RAG-based grounding, knowledge editing |
| Calibration & uncertainty | ~54 | Confidence estimation, overconfidence |

**80/20**: ~40 papers on hallucination benchmarking and RAG-based mitigation
cover the dominant research approaches.

---

### B09 · Long Context & Context Window — 28 papers

Extending what models can attend to at once.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Long context techniques | ~15 | RoPE, ALiBi, sliding window |
| Context window extension | ~13 | 128k+ context, positional extrapolation |

**80/20**: ~8 papers on positional encoding + context extension techniques
(RoPE, YaRN, LongLoRA) cover the technical foundations.

---

### B10 · Multimodal & Vision-Language — 274 papers ⭐

Models that understand both images and text.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Vision-language models (general) | ~120 | LLaVA, GPT-4V, Flamingo |
| Multimodal alignment | ~85 | Image-text alignment, cross-modal grounding |
| Claude multimodal | ~69 | Claude Vision, document understanding |

**80/20**: ~30 foundational papers on vision-language alignment and instruction
tuning (LLaVA, InstructBLIP) define the current paradigm.

---

### B11 · General LLM Safety — 86 papers

Broad safety concerns for large language models.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| LLM safety frameworks | ~45 | Safety evaluation, risk taxonomies |
| Model safety training | ~41 | Safety fine-tuning, RLHF for safety |

**80/20**: ~20 papers on safety evaluation frameworks and RLHF-for-safety
training protocols form the core reference set.

---

### B12 · Reasoning & Chain-of-Thought — 449 papers ⭐ (largest cluster)

Enabling step-by-step reasoning in LLMs.

| Sub-topic | Count | Highlights |
|-----------|-------|-----------|
| Chain-of-thought prompting | ~200 | Wei et al. CoT, zero-shot CoT |
| Reasoning faithfulness | ~90 | Does the chain reflect actual computation? |
| Complex reasoning benchmarks | ~100 | GSM8K, MATH, BIG-Bench Hard |
| CoT faithfulness / transparency | ~59 | Post-hoc rationalization detection |

**80/20**: ~20 papers from the core CoT line (Wei et al., Self-Consistency, ToT,
Constitutional AI's use of CoT) plus ~10 faithfulness papers are canonical.

---

## Cross-Cutting Findings

1. **Reasoning is the dominant theme**: B12 (449 papers) is the largest cluster,
   reflecting that chain-of-thought and reasoning capabilities are the central
   competitive axis for frontier LLMs including Claude.

2. **Interpretability is growing fast**: B04 (177 papers) has grown 8× from
   2021 to 2025, driven by Anthropic's mechanistic interpretability program and
   sparse autoencoder research.

3. **Safety is multi-faceted**: B06 (163 papers) covers adversarial attacks,
   alignment methods, and deceptive behavior — each requiring distinct mitigations.

4. **Multimodal rapidly expanding**: B10 (274 papers) reflects the shift from
   text-only to multimodal Claude models (Claude 3's vision capabilities).

5. **Hallucination remains unsolved**: B08 (199 papers) is the third-largest
   cluster, indicating hallucination reduction is still an open, active problem
   despite 5+ years of research.

---

## arXiv Category Breakdown

| Category | Papers | Focus Area |
|----------|--------|-----------|
| cs.CL | 802 | Computation & Language (core NLP/LLM research) |
| cs.LG | 721 | Machine Learning (training methods, scaling) |
| cs.AI | 216 | Artificial Intelligence (alignment, safety) |
| cs.CV | 181 | Computer Vision (multimodal research) |
| cs.CR | 114 | Cryptography & Security (adversarial, jailbreaks) |
| cs.SE | 83 | Software Engineering (code generation, AI tools) |

---

[中文说明](README.zh-CN.md) | [知识文档](anthropic-claude.md) | [返回主目录](../README.md)
