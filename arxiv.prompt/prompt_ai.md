[**中文版**](prompt_ai.zh-CN.md)

# AI/LLM Prompt Engineering: 50 Core Techniques (2023–2026)

> A systematic analysis of **4,780** AI/LLM prompt-related paper abstracts from arXiv CS categories, 2023–2026.
> Organized by use case and scenario for direct application and comparison.
> The consolidated content covers **50 core techniques** across **8 major categories** and **9 combined application solutions**.

**Paper Distribution by Year:**

| Year | Papers |
|------|--------|
| 2023 | 1,085 |
| 2024 | 1,478 |
| 2025 | 1,817 |
| 2026 | 400 |

**Table of Contents:**

| Category | Technique # | Focus |
|------|---------|------|
| I. Reasoning & Chain-of-Thought | 1-6 | Enhancing model reasoning capability |
| II. Examples & In-Context Learning | 7-11 | Using examples to guide output |
| III. Prompt Design & Formatting | 12-16 | Fundamental prompt construction methods |
| IV. Orchestration & Workflows | 17-22 | Multi-step / multi-module collaboration |
| V. Optimization & Compression | 23-28 | Engineering-driven efficiency improvements |
| VI. Quality & Robustness | 29-33 | Evaluation and stability enhancement |
| VII. Defense & Protection | 34-41 | Security defense techniques |
| VIII. ⚠️ Attacks & Penetration (Security Research) | 42-50 | Red-team testing and attack methods |

---

# I. Reasoning & Chain-of-Thought (Enhancing Model Reasoning)

## 1. Chain-of-Thought Prompting

| Field | Content |
|------|------|
| **Template** | Add "Let's think step by step" to the prompt or provide examples with reasoning traces. E.g.: `Q: {question}\nA: Let's think step by step. First, ... Then, ... Therefore, the answer is {answer}` |
| **Principle** | Guides the model to generate intermediate reasoning steps before outputting the answer. Google DeepMind found that even without explicit prompts, CoT reasoning can be triggered through non-greedy decoding paths, suggesting CoT is an intrinsic model capability. However, research also shows CoT explanations may not faithfully reflect the model's actual decision process (deviation rate up to ~36%). |
| **Source** | arXiv:2402.10200 (238 citations), arXiv:2305.04388 (912 citations), 342 related papers |
| **Use Cases** | Mathematical reasoning, logical reasoning, multi-step computation, complex Q&A |

---

## 2. Plan-and-Solve Prompting

| Field | Content |
|------|------|
| **Template** | Zero-shot two-stage: first plan (decompose task into subtasks), then execute step by step. E.g.: `Let's first understand the problem and devise a plan to solve it. Then, let's carry out the plan and solve the problem step by step.` The PS+ variant adds detail requirements to reduce computation errors. |
| **Principle** | Adds an explicit planning phase on top of Zero-shot-CoT, addressing "missing steps" and "computation errors." Substantially outperforms Zero-shot-CoT across 10 datasets on GPT-3, matching or exceeding few-shot methods. |
| **Source** | arXiv:2305.04091 (640 citations) |
| **Use Cases** | Math word problems, multi-step reasoning, zero-shot reasoning scenarios |

---

## 3. Structured Chain-of-Thought for Code

| Field | Content |
|------|------|
| **Template** | Force intermediate reasoning to follow sequential/branching/looping program structures before generating code. E.g.: output pseudocode structure first → then generate actual code. |
| **Principle** | General CoT is not well-suited for code tasks. SCoT constrains reasoning to program structures, achieving up to ~13.79% higher Pass@1 on HumanEval/MBPP compared to vanilla CoT. |
| **Source** | arXiv:2305.06599 (286 citations) |
| **Use Cases** | Code generation, algorithm implementation, competitive programming |

---

## 4. CoT Separator Enhancement

| Field | Content |
|------|------|
| **Template** | Append separators at the end of each CoT example. E.g.: `Example 1: {reasoning} → {answer}\n---\nExample 2: {reasoning} → {answer}\n---\nQuestion: {new question}` |
| **Principle** | Separators help the model distinguish boundaries between different reasoning examples, reducing information overload in dense prompts. Significantly improves performance on GSM8K, AQuA, and similar tasks. |
| **Source** | arXiv:2402.10645 |
| **Use Cases** | Multi-example CoT, complex reasoning |

---

## 5. Robust CoT with Noisy Rationales

| Field | Content |
|------|------|
| **Template** | **CD-CoT**: Contrast multiple noisy rationales with one clean rationale, performing explore/exploit in both input and output spaces. |
| **Principle** | Existing LLMs are highly fragile to noisy reasoning chains. CD-CoT improves average accuracy by ~17.8% through contrasting clean and noisy rationales, requiring minimal clean supervision. |
| **Source** | arXiv:2410.23856 (51 citations) |
| **Use Cases** | Tasks with uncontrollable rationale quality, retrieval-augmented CoT |

---

## 6. Reasoning Without Prompting

| Field | Content |
|------|------|
| **Template** | No explicit CoT prompt needed — trigger intrinsic CoT by exploring non-greedy decoding paths (top-k alternative tokens). LeCo learns from correct steps using step-wise logits confidence. |
| **Principle** | CoT capability is inherent to pretrained models. CoT-decoding outperforms greedy decoding on reasoning benchmarks. LeCo saves tokens while improving performance. |
| **Source** | arXiv:2402.10200 (238 citations), LeCo arXiv:2403.19094 |
| **Use Cases** | Automated reasoning, scenarios with low prompt design requirements |

---

# II. Examples & In-Context Learning (Using Examples to Guide Output)

## 7. Few-Shot / In-Context Learning

| Field | Content |
|------|------|
| **Template** | Provide 1–5 input-output examples in the prompt. Research shows even a single example can significantly reduce prompt sensitivity. The number and quality of examples strongly affect performance — bad examples can be harmful. |
| **Principle** | Demonstrates task format and expected output patterns through examples. The POSIX metric shows few-shot is the most reliable means of reducing sensitivity. |
| **Source** | POSIX (arXiv:2410.02185), arXiv:2301.07069 (392 citations), 783 related papers |
| **Use Cases** | Text classification, NER, translation, formatted output |

---

## 8. Auto-Demo Prompting

| Field | Content |
|------|------|
| **Template** | In batch processing, use the model's earlier outputs as examples for subsequent questions, without manual authoring. |
| **Principle** | Leverages the model's own high-quality outputs as dynamic demonstrations, reducing batch inference degradation. |
| **Source** | arXiv:2410.01724 |
| **Use Cases** | Batch inference, tasks with poor zero-shot performance, cold start |

---

## 9. Mixture-of-Expert Prompts

| Field | Content |
|------|------|
| **Template** | Cluster examples by semantics, generate specialized instructions for each cluster, and route to the best-matching expert prompt at inference. ~81% win rate. |
| **Principle** | A single prompt cannot cover all subtypes of a task; MoE-style prompt combinations cover diverse inputs. |
| **Source** | arXiv:2407.00256 |
| **Use Cases** | Classification with diverse inputs, complex NLP tasks |

---

## 10. Self-Consistency Prompting

| Field | Content |
|------|------|
| **Template** | Sample multiple reasoning paths for the same question and select the answer by majority vote. OpenMedLM combines kNN examples + CoT + self-consistency. |
| **Principle** | Multiple sampling leverages diversity to reduce variance. OpenMedLM surpassed fine-tuned SOTA on MedQA purely through prompt engineering. |
| **Source** | OpenMedLM (arXiv:2402.19371) 82 citations |
| **Use Cases** | Medical Q&A, mathematical reasoning, high-accuracy multiple-choice |

---

## 11. Multi-Prompt LLM Evaluation

| Field | Content |
|------|------|
| **Template** | Evaluate models using a diverse set of prompts rather than a single template. PromptEval can estimate performance quantiles for ~100 variants at roughly 2× the budget of a single prompt. |
| **Principle** | Single-prompt SOTA claims are fragile over millions of instances. Multi-prompt evaluation better reflects true capabilities. |
| **Source** | arXiv:2401.00595 (264 citations), PromptEval (arXiv:2405.17202) |
| **Use Cases** | Model evaluation, prompt selection, benchmark design |

---

# III. Prompt Design & Formatting (Fundamental Construction Methods)

## 12. Prompt Pattern Catalog

| Field | Content |
|------|------|
| **Template** | Similar to software design patterns, defines reusable prompt patterns (e.g., Output Automater, Persona, Template, etc.) that can be composed. |
| **Principle** | Systematizes prompt engineering into a pattern language, providing a structured framework to guide design. |
| **Source** | arXiv:2302.11382 (1,646 citations, **highest in the corpus**) |
| **Use Cases** | All prompt design, team collaboration standardization |

---

## 13. Prompt Formatting

| Field | Content |
|------|------|
| **Template** | Keep content identical but vary the format (plain text, Markdown, JSON, YAML, XML). GPT-3.5 can fluctuate ~40% due to format alone; open-source models can swing ~76 percentage points. |
| **Principle** | Format has a massive impact on performance. Larger models are more robust but one cannot assume a fixed optimal format. |
| **Source** | arXiv:2411.10541 (165 citations), arXiv:2310.11324 (626 citations) |
| **Use Cases** | All tasks, especially code, classification, structured output |

---

## 14. Role-Play Prompting

| Field | Content |
|------|------|
| **Template** | Assign a role to trigger domain knowledge and reasoning. E.g.: `You are a {domain} expert...` Research shows role-playing substantially outperforms "think step by step" in zero-shot reasoning. |
| **Principle** | Role assignment not only triggers domain knowledge but also activates stronger reasoning capabilities. |
| **Source** | arXiv:2308.07702 (358 citations), 250 related papers |
| **Use Cases** | Zero-shot reasoning, professional Q&A, style-specific generation |

---

## 15. Emotional Stimulus Prompting

| Field | Content |
|------|------|
| **Template** | Add emotional motivators to the prompt. The APGP framework automatically integrates emotional stimuli + structured scaffolding. |
| **Principle** | Emotional stimuli can activate model attention. System 1/2 cognitive process-related prompts can reduce social bias. |
| **Source** | APGP (arXiv:2404.10500), arXiv:2404.17218, 150 related papers |
| **Use Cases** | Complex problem solving, bias reduction |

---

## 16. Butterfly Effect of Prompts

| Field | Content |
|------|------|
| **Template** | Extremely minor edits (trailing spaces, XML tags) can flip model answers. |
| **Principle** | All prompt design must strictly control variables. Format changes during LLM data labeling cause label inconsistencies. |
| **Source** | arXiv:2401.03729 (98 citations) |
| **Use Cases** | Data labeling quality control, prompt robustness testing |

---

# IV. Orchestration & Workflows (Multi-Step / Multi-Module Collaboration)

## 17. Prompt Chaining vs. Stepwise Prompting

| Field | Content |
|------|------|
| **Template** | **Prompt Chaining**: Send separate Draft → Critique → Refine calls. **Stepwise Prompting**: Single prompt requesting multiple steps. |
| **Principle** | Prompt chaining outperforms single-prompt multi-step simulation. Stepwise prompting may only "simulate" rather than truly perform iterative optimization. |
| **Source** | arXiv:2406.00507, 522 chaining-related papers |
| **Use Cases** | Text summarization, content creation, iterative generation refinement |

---

## 18. Meta-Prompting

| Field | Content |
|------|------|
| **Template** | One LLM acts as a "conductor" to decompose tasks, invokes multiple "expert" LLM instances for subtasks, then integrates and verifies. 17.1% higher than standard prompting. |
| **Principle** | Uses one model for task decomposition and result integration, with each expert focusing on a sub-problem. |
| **Source** | Stanford arXiv:2401.12954 (132 citations) |
| **Use Cases** | Complex multi-step tasks, cross-domain analysis |

---

## 19. Prompt Ensemble

| Field | Content |
|------|------|
| **Template** | Use multiple different prompt variants for the same task, aggregate results by selecting the best or voting. MCS-SQL achieves 65.5% on BIRD. |
| **Principle** | Single-prompt performance is unstable; multi-prompt ensemble leverages diversity to reduce variance. |
| **Source** | MCS-SQL (arXiv:2405.07467) 105 citations, 163 related papers |
| **Use Cases** | Text-to-SQL, high-precision scenarios |

---

## 20. Flow Engineering for Code

| Field | Content |
|------|------|
| **Template** | Test-driven multi-stage iteration: Spec → Tests → Code → Verify → Fix. AlphaCodium raised GPT-4 pass@5 from 19% to 44%. |
| **Principle** | Single prompts cannot handle complex programming tasks; test-driven iteration focuses each step on one sub-goal. |
| **Source** | AlphaCodium (arXiv:2401.08500) 112 citations |
| **Use Cases** | Competitive programming, complex function generation |

---

## 21. Prompt Programming Languages

| Field | Content |
|------|------|
| **Template** | **APPL**: Python-native prompt embedding with async parallelism. **PDL**: YAML declarative. **SPML**: Attack-resistant DSL. |
| **Principle** | Raw string concatenation is fragile and error-prone; dedicated DSLs provide structured control and reusability. |
| **Source** | APPL (arXiv:2406.13161), PDL (arXiv:2410.19135) |
| **Use Cases** | Complex LLM applications, agent orchestration |

---

## 22. Multi-Agent Prompt & Topology Optimization

| Field | Content |
|------|------|
| **Template** | **MASS**: Alternates between block-level prompt optimization, workflow topology search, and global prompt optimization. |
| **Principle** | Multi-agent performance depends not only on individual prompts but also on inter-agent topology and collaboration patterns. MASS jointly optimizes and substantially outperforms baselines. |
| **Source** | arXiv:2502.02533 (64 citations) |
| **Use Cases** | Multi-agent system design, complex workflows |

---

# V. Optimization & Compression (Engineering-Driven Efficiency)

## 23. Automatic Prompt Optimization

| Field | Content |
|------|------|
| **Template** | **APO** (2023): Natural-language "gradients" + beam search, up to ~31% improvement. **Promptbreeder**: Self-referential evolution. **PromptWizard** (2024): Top across 45 tasks. **GEPA** (2025): Reflective evolution, ~6% above GRPO with ~35× fewer rollouts. |
| **Principle** | Continuous progress from 2023 gradient simulation to 2025 reflective evolution. SPO matches SOTA without external labels. |
| **Source** | APO (arXiv:2305.03495) 591 citations, Promptbreeder (arXiv:2309.16797) 396 citations, GEPA (arXiv:2507.19457) 96 citations, 384 related papers |
| **Use Cases** | Production-grade prompt tuning, RAG pipelines |

---

## 24. Prompt Compression

| Field | Content |
|------|------|
| **Template** | **Gist Tokens** (2023): ~26× compression. **LongLLMLingua** (2023): QA +21.4%, tokens −4×. **LLMLingua-2** (2024): 3–6× faster. **Nano-Capsulator**: ~81% reduction. |
| **Principle** | Long prompts cause high latency and cost. Continuous evolution from learnable gist tokens to distilled classifiers. |
| **Source** | Gist Tokens (arXiv:2304.08467) 320 citations, LongLLMLingua (arXiv:2310.06839) 371 citations, LLMLingua-2 (arXiv:2403.12968) 225 citations, 117 related papers |
| **Use Cases** | Long documents, RAG, API cost optimization |

---

## 25. Prompt Rewriting

| Field | Content |
|------|------|
| **Template** | PRewrite uses RL to rewrite weak prompts. SCULPT represents long prompts as trees and optimizes via a Critic-Actor loop. |
| **Principle** | Automatic rewriting can reliably improve non-expert users' prompt effectiveness. |
| **Source** | PRewrite (arXiv:2401.08189), SCULPT (arXiv:2410.20788) |
| **Use Cases** | Scenarios with uncontrollable user prompt quality |

---

## 26. Prompt + Fine-Tuning Joint Optimization

| Field | Content |
|------|------|
| **Template** | BetterTogether/DSPy: Alternating weight optimization and prompt optimization. ~60% above prompt optimization alone, ~6% above fine-tuning alone. |
| **Principle** | Each approach alone has a ceiling; joint optimization creates mutual reinforcement. |
| **Source** | arXiv:2407.10930 (40 citations) |
| **Use Cases** | RAG pipelines, modular LLM applications |

---

## 27. Self-Supervised Prompt Optimization

| Field | Content |
|------|------|
| **Template** | **SPO**: LLM pairwise output comparison ranks prompts, then an optimizer aligns — no external labels needed. |
| **Principle** | Matches or surpasses SOTA at a fraction of the API cost and sample size. |
| **Source** | SPO (arXiv:2502.06855) 29 citations |
| **Use Cases** | Prompt optimization without labeled data |

---

## 28. Soft Prompt Tuning

| Field | Content |
|------|------|
| **Template** | Prepend learnable continuous vectors to the input. LoPA (low-rank decomposition), SuperPos-Prompt (multi-embedding superposition), GenPI (internalizing prompts into the model). |
| **Principle** | Extremely small parameter count can match full fine-tuning. GenPI eliminates the need for explicit prompts at inference time. |
| **Source** | LoPA (arXiv:2405.15282), SuperPos-Prompt (arXiv:2406.05279), 519 related papers |
| **Use Cases** | Resource-constrained adaptation, multi-tenant services |

---

# VI. Quality & Robustness (Evaluation & Stability Enhancement)

## 29. Prompt Bias Calibration

| Field | Content |
|------|------|
| **Template** | Estimate "prompt-only" bias representations at inference time and subtract from activations. Causal debiasing: apply front-door adjustment using CoT as a mediator. |
| **Principle** | Prompts introduce non-trivial biases. Debiasing improves factual retrieval by up to ~10 percentage points. Causal methods are effective across 7 NLP datasets. |
| **Source** | arXiv:2403.09963, Causal Prompting (arXiv:2403.02738), 358 related papers |
| **Use Cases** | Factual knowledge extraction, fairness, debiasing |

---

## 30. Prompt Sensitivity Assessment

| Field | Content |
|------|------|
| **Template** | **POSIX**: Measures variation after semantically equivalent substitutions. **ProSA**: Instance-level decoding confidence analysis. **PromptRobust**: 4,788 adversarial prompt benchmark. **PromptSET** (2025): Sensitivity prediction task. |
| **Principle** | Larger models do not reliably reduce sensitivity. Few-shot helps the most. Current methods still perform poorly at sensitivity prediction. |
| **Source** | PromptRobust (arXiv:2306.04528) 246 citations, POSIX (arXiv:2410.02185), ProSA (arXiv:2410.12405) 128 citations |
| **Use Cases** | Prompt quality assurance, pre-deployment robustness testing |

---

## 31. Prompt Perturbation Consistency Learning

| Field | Content |
|------|------|
| **Template** | PPCL: Applies consistency regularization during fine-tuning against homophone/synonym/paraphrase perturbations of prompts. |
| **Principle** | Recovers most performance degradation caused by perturbations, using fewer samples than data augmentation. |
| **Source** | PPCL (arXiv:2402.15833) |
| **Use Cases** | Deployments requiring high robustness |

---

## 32. LLM-as-a-Judge Prompting

| Field | Content |
|------|------|
| **Template** | Use an LLM as an evaluator to score outputs. Different evaluation templates lead to inconsistent scores; diverse templates and interpretable metrics are needed. |
| **Principle** | Evaluation prompt design has a massive impact on scoring. |
| **Source** | arXiv:2408.13006 (69 citations) |
| **Use Cases** | Model evaluation, alignment assessment, automated benchmarking |

---

## 33. Domain-Specific Prompting

| Field | Content |
|------|------|
| **Sub-techniques** | **Medical**: OpenMedLM (kNN + CoT + self-consistency) surpasses fine-tuned SOTA. **Multilingual**: CoTR translates first, executes, then translates back — significant gains for low-resource languages. **Text-to-SQL**: PET-SQL two-round progressive prompt, Spider SOTA 87.6%. **Knowledge Graph**: KGP constructs KG + agent traversal to collect context. **Synthetic Data**: Magpie uses empty prompts for large-scale training data generation. **Knowledge Editing**: RECIPE continuous prompt + retrieval for lifelong editing. |
| **Principle** | Different domains require customized prompt strategies; general prompts cannot optimally cover all scenarios. |
| **Source** | OpenMedLM (arXiv:2402.19371), CoTR (arXiv:2409.04512), PET-SQL (arXiv:2403.09732), KGP (arXiv:2308.11730) 267 citations, Magpie (arXiv:2406.08464) 296 citations, RECIPE (arXiv:2405.03279) |
| **Use Cases** | All vertical domains |

---

# VII. Defense & Protection (Security Defense Techniques)

> This chapter covers techniques for protecting LLM applications from attacks, intended for security engineers and application developers.

## 34. Prompt Injection Defense — Data Spotlighting

| Field | Content |
|------|------|
| **Template** | Apply source-marking transformations to untrusted data (e.g., encoding, delimiting, tag wrapping) so the model distinguishes instructions from data. |
| **Principle** | Indirect prompt injection hides malicious instructions in retrieved data. Spotlighting reduces injection success rate from >50% to <2% without degrading normal task performance. |
| **Source** | arXiv:2403.14720 (133 citations) |
| **Use Cases** | RAG systems, scenarios handling untrusted external input |

---

## 35. Prompt Injection Defense — Structured Separation (Structured Queries)

| Field | Content |
|------|------|
| **Template** | **StruQ**: Separates instructions and data into structured channels, fine-tunes the model to only follow the instruction channel. **Signed-Prompt**: Uses signatures to mark trusted instruction segments. |
| **Principle** | Analogous to SQL parameterized queries for injection prevention — structurally separates untrusted input from instructions at the root level. |
| **Source** | StruQ (arXiv:2402.06363) 207 citations, Signed-Prompt (arXiv:2401.07612) |
| **Use Cases** | LLM application security, agent systems |

---

## 36. Prompt Injection Defense — Preference-Based Alignment

| Field | Content |
|------|------|
| **Template** | **SecAlign**: Constructs preference pairs (injection → safe vs. unsafe responses), DPO-trains the model to prefer following legitimate instructions. Injection success rate <10%. **Meta SecAlign** (2025) generalizes across models. |
| **Principle** | Frames injection defense as an alignment problem, using preference optimization to make models naturally resist injection. |
| **Source** | SecAlign (arXiv:2410.05451) 89 citations, Meta SecAlign (arXiv:2507.02735) 36 citations |
| **Use Cases** | Production-grade security hardening |

---

## 37. Prompt Injection Detection

| Field | Content |
|------|------|
| **Template** | **DataSentinel** (2025): Game-theoretic minimax fine-tuned detector. **PromptShield** (2025): Curated training set + low-FPR detector. **PromptArmor** (2025): Auxiliary LLM detects and removes injected text, FPR/FNR <1%, ASR <1%. |
| **Principle** | Injection detection requires simultaneously low false positives and low false negatives. DataSentinel remains effective against adaptive attacks. |
| **Source** | DataSentinel (arXiv:2504.11358) 70 citations, PromptShield (arXiv:2501.15145) 33 citations, PromptArmor (arXiv:2507.15219) 51 citations |
| **Use Cases** | Deployment-level real-time injection protection |

---

## 38. Injection-Immune Architecture

| Field | Content |
|------|------|
| **Template** | **CaMeL** (2025): Trusted/untrusted data flow separation + capability policies, 77% task completion + provable safety. **Prompt Flow Integrity**: Agent isolation + privilege escalation prevention. **Design Pattern Catalog**: Systematized anti-injection architecture patterns. |
| **Principle** | 2025 security research shifted from "patch-based defense" to "architecture-level immunity," providing provable safety guarantees. This represents a fundamental paradigm shift in prompt security. |
| **Source** | CaMeL (arXiv:2503.18813) 95 citations, PFI (arXiv:2503.15547) 33 citations, Design Patterns (arXiv:2506.08837) 35 citations |
| **Use Cases** | Enterprise LLM applications, critical infrastructure |

---

## 39. Multi-Agent Security

| Field | Content |
|------|------|
| **Template** | **MELON** (masked re-run attack detection), **RTBAS** (information flow control + LM-judge), **Reverse Attack Defense** (repurposes attack mechanisms to flip intent, achieving SOTA without training). |
| **Principle** | In multi-agent systems, malicious instructions can propagate across agents. MELON is strongest on AgentDojo; RTBAS has ~2% utility loss. |
| **Source** | MELON (arXiv:2502.05174) 29 citations, RTBAS (arXiv:2502.08966) 28 citations, arXiv:2411.00459 (32 citations) |
| **Use Cases** | Agent system security, tool integration |

---

## 40. Prompt Theft Protection

| Field | Content |
|------|------|
| **Template** | **PromptKeeper**: Hypothesis testing to detect leakage + dummy prompt regeneration. **Prompt Obfuscation**: Replaces original prompt with a functionally equivalent obfuscated version, resistant to de-obfuscation attacks. |
| **Principle** | Even aligned models are highly susceptible to prompt extraction. Obfuscation hides original wording while maintaining functional equivalence. |
| **Source** | PromptKeeper (arXiv:2412.13426), Obfuscation (arXiv:2409.11026) |
| **Use Cases** | Commercial prompt protection, SaaS intellectual property |

---

## 41. Prompt Unlearning & Caching

| Field | Content |
|------|------|
| **Sub-techniques** | **Unlearning**: ECO suppresses specific knowledge through prompt embedding perturbation (universal across 0.5B–236B). SPUL learns soft prompts for unlearning. **Caching**: Distilled embeddings determine cache usability (AUC 0.51→0.81). Preble distributed scheduling reuses KV-cache. |
| **Principle** | Unlearning enables compliance without retraining. Caching drastically reduces repeated inference costs. |
| **Source** | ECO (arXiv:2406.07933) 101 citations, Preble (arXiv:2407.00023) 50 citations, 462 papers combined |
| **Use Cases** | GDPR compliance, high-concurrency services, cost optimization |

---

# VIII. ⚠️ Attacks & Penetration (Security Research)

> **Warning: This chapter is intended solely for security research, red-team testing, and defense validation.**
> Understanding attack methods is a prerequisite for building effective defenses.

## 42. Indirect Prompt Injection Attack

| Field | Content |
|------|------|
| **Method** | Inject malicious instructions into external data (web pages, documents, emails) that the LLM will retrieve; when the LLM reads this data, it automatically executes the attacker's instructions. |
| **Impact** | First systematically revealed in 2023: HouYi compromised 31/36 real-world applications (including Bing Chat, Notion, etc.), enabling prompt theft, user data exfiltration, and unconstrained model manipulation. |
| **Technical Details** | HouYi three-stage approach: hidden pre-prompt + context-splitting injection + malicious payload. Patterns derived from traditional web injection techniques. |
| **Source** | HouYi (arXiv:2306.05499) 657 citations, arXiv:2302.12173 (989 citations) |
| **Defense Reference** | → Techniques 34–38 |

---

## 43. Manual Jailbreak Prompts

| Field | Content |
|------|------|
| **Method** | Manually designed prompt templates that bypass safety alignment (e.g., DAN "Do Anything Now"). 10 patterns, 3 major categories, 40 scenarios. |
| **Impact** | Wild templates collected by JailbreakHub achieve ASR of ~0.95 on GPT-3.5/4. Some templates survive online for months. Many users can construct effective jailbreaks without deep LLM knowledge. |
| **Technical Details** | 10 jailbreak patterns categorized into role-playing, scenario construction, and logic bypass. |
| **Source** | DAN (arXiv:2308.03825) 535 citations, arXiv:2305.13860 (657 citations), arXiv:2403.17336 (94 citations) |
| **Defense Reference** | → Technique 36 (SecAlign), 38 (Architecture Immunity) |

---

## 44. Automated Jailbreak Generation

| Field | Content |
|------|------|
| **Method** | **AutoDAN**: Genetic algorithm generates semantically coherent stealthy jailbreak prompts that evade perplexity detection. **GPTFUZZER**: AFL-style fuzz testing, mutating seed templates, >90% ASR. **Rainbow Teaming**: Quality-diversity search producing hundreds of diverse prompts with >90% ASR. |
| **Impact** | Automation far exceeds manual scale and can continuously generate new variants. AutoDAN is automated + stealthy + transferable. |
| **Technical Details** | AutoDAN uses hierarchical genetic algorithms to maintain semantic coherence. GPTFUZZER uses selection + mutation + judge-model closed loop. Rainbow Teaming maximizes attack diversity through quality-diversity search. |
| **Source** | AutoDAN (arXiv:2310.04451) 658 citations, GPTFUZZER (arXiv:2309.10253) 557 citations, Rainbow Teaming (arXiv:2402.16822) 164 citations |
| **Defense Reference** | → Technique 35 (RPO defense suffix) |

---

## 45. Prompt Decomposition Attack

| Field | Content |
|------|------|
| **Method** | **DrAttack**: Splits a harmful request into multiple seemingly innocuous sub-prompts, reassembles via ICL and synonym substitution. Achieves ~78% ASR on GPT-4 with only ~15 queries. |
| **Impact** | Each fragment appears harmless and bypasses safety checks; extremely query-efficient, far surpassing traditional methods. |
| **Technical Details** | Decompose → synonym substitution → ICL-guided reassembly → model implicitly concatenates to recover original intent. |
| **Source** | DrAttack (arXiv:2402.16914) 100 citations |
| **Defense Reference** | → Technique 37 (Injection Detection), 38 (Architecture Immunity) |

---

## 46. Sequential Prompt Chain Attack

| Field | Content |
|------|------|
| **Method** | **SequentialBreak**: Embeds malicious instructions within a benign multi-step conversation chain (e.g., quiz banks, dialogues, games), completed in a single user query. |
| **Impact** | Surpasses ASR of prior jailbreak methods, revealing weaknesses in sequential context defenses. |
| **Technical Details** | Exploits the model's "trust inertia" when processing intermediate steps in long sequences. |
| **Source** | SequentialBreak (arXiv:2411.06426) 13 citations |
| **Defense Reference** | → Technique 38 (Architecture Immunity), 39 (Multi-Agent Security) |

---

## 47. Prompt Extraction & Stealing

| Field | Content |
|------|------|
| **Method** | **output2prompt**: Reverse-engineers system prompts from normal outputs (no logits or jailbreaking needed), with zero-shot cross-LLM transferability. **PLeak**: Specifically targets prompt leakage in LLM applications. Even aligned models are extremely vulnerable to simple extraction techniques. |
| **Impact** | Stolen commercial prompts mean loss of competitive advantage and intellectual property leakage. |
| **Technical Details** | output2prompt uses learning + sparse coding to recover prompts from regular outputs. PLeak targets application-layer leakage paths. |
| **Source** | output2prompt (arXiv:2405.15012), PLeak (arXiv:2405.06823) 127 citations |
| **Defense Reference** | → Technique 40 (Theft Protection) |

---

## 48. Learned Injection Triggers

| Field | Content |
|------|------|
| **Method** | **Neural Exec**: Learns injection triggers via differentiable/search optimization rather than using fixed hand-crafted strings. |
| **Impact** | Novel form, surface-level innocuous, capable of penetrating multi-stage RAG pipelines. Reveals fundamental limitations of blocklist-based defense strategies. |
| **Technical Details** | Gradient optimization / search generates optimal triggers that appear indistinguishable from normal text. |
| **Source** | Neural Exec (arXiv:2403.03792) 66 citations |
| **Defense Reference** | → Technique 37 (DataSentinel Detection), 38 (Architecture Immunity) |

---

## 49. Adaptive Attacks on Defenses

| Field | Content |
|------|------|
| **Method** | Custom-tailored attacks against published defense schemes. A 2025 study systematically tested 8 published defenses — **each was broken with >50% ASR**. |
| **Impact** | Demonstrates that nearly all non-architectural defenses are fragile against adaptive attackers. Defenses must be evaluated under adaptive attacks. |
| **Technical Details** | Analyzes each defense mechanism's weaknesses and crafts targeted bypasses. Google's continuous red-teaming of Gemini shows only sustained adversarial evaluation can effectively harden systems. |
| **Source** | arXiv:2503.00061 (61 citations), Gemini experience (arXiv:2505.14534) 27 citations |
| **Defense Reference** | → Technique 38 (Architecture Immunity) is currently the most effective countermeasure |

---

## 50. Injection Formalization & Benchmarking

| Field | Content |
|------|------|
| **Method** | Unified framework defining all prompt injection variants (existing attacks are all special cases), composable to produce novel attacks. **AgentDojo**: Dynamic agent benchmark. **WASP**: Web agent security benchmark (~86% partial success rate). |
| **Significance** | Standardizes attack taxonomy and evaluation methodology, driving systematic defense research. Complete matrix of 5 attacks × 10 defenses × 10 LLMs × 7 tasks. |
| **Source** | Formalization framework (arXiv:2310.12815) 263 citations, AgentDojo (arXiv:2406.13352) 100 citations, WASP (arXiv:2504.18575) 65 citations |
| **Defense Reference** | → Techniques 34–39 (all) |

---

# Combined Application Solutions

### Solution A: High-Accuracy Reasoning

```
CoT (1) + Plan-and-Solve (2) + Separators (4) + Self-Consistency (10) + Ensemble (19)
```

### Solution B: Full-Stack Secure Deployment

```
Architecture Immunity (38) + SecAlign (36) + PromptArmor Detection (37) + Theft Protection (40)
```

### Solution C: Automated Prompt Pipeline

```
GEPA Optimization (23) + Compression (24) + SPO Self-Supervised (27) + Sensitivity Assessment (30)
```

### Solution D: Complex Task Divide-and-Conquer

```
Meta-Prompting (18) + Prompt Chaining (17) + Multi-Agent Design (22) + Flow Engineering for Code (20)
```

### Solution E: Medical / High-Accuracy Q&A

```
Role-Play (14) + CoT (1) + Self-Consistency (10) + Bias Calibration (29) + Knowledge Graph (33)
```

### Solution F: Low-Resource / Cold Start

```
Auto-Demo (8) + Cross-Lingual Prompting (33) + Mixture-of-Expert (9) + Synthetic Data (33)
```

### Solution G: Intelligent Database Querying

```
Text-to-SQL (33) + Prompt Ensemble (19) + Prompt Chaining (17)
```

### Solution H: Security Red-Team Testing (Authorization Required)

```
Automated Jailbreak (44) + Decomposition Attack (45) + Adaptive Attack (49) + Formalization Benchmark (50)
```

### Solution I: Full-Stack Prompt Engineering

```
Pattern Catalog (12) + Formatting (13) + DSL (21) + Auto-Optimization (23) + Caching (41)
```

---

# Quick Reference

## 🔵 Positive Techniques (Design / Optimization / Defense)

| # | Technique | Category | Core Keywords | Year |
|---|------|------|-----------|------|
| 1 | Chain-of-Thought CoT | Reasoning | step-by-step | 2022→2024 |
| 2 | Plan-and-Solve | Reasoning | Zero-shot planning | 2023 |
| 3 | Structured CoT for Code | Reasoning | SCoT | 2023 |
| 4 | CoT Separators | Reasoning | Example boundaries | 2024 |
| 5 | Noise-Tolerant CoT | Reasoning | CD-CoT | 2024 |
| 6 | Reasoning Without Prompting | Reasoning | CoT-decoding | 2024 |
| 7 | Few-Shot / ICL | Examples | Example-driven | Classic |
| 8 | Auto-Demo Generation | Examples | Dynamic demos | 2024 |
| 9 | Mixture-of-Expert Prompts | Examples | MoE | 2024 |
| 10 | Self-Consistency | Examples | Majority vote | 2023 |
| 11 | Multi-Prompt Evaluation | Examples | Multi-template | 2024 |
| 12 | Pattern Catalog | Design | Design patterns | 2023 |
| 13 | Prompt Formatting | Design | JSON/XML | 2023 |
| 14 | Role-Play | Design | Persona | 2023 |
| 15 | Emotional Stimulus | Design | Motivation | 2024 |
| 16 | Butterfly Effect | Design | Tiny changes | 2024 |
| 17 | Prompt Chaining | Orchestration | Multi-turn divide | 2024 |
| 18 | Meta-Prompting | Orchestration | Conductor | 2024 |
| 19 | Prompt Ensemble | Orchestration | Multi-prompt vote | 2024 |
| 20 | Flow Engineering for Code | Orchestration | AlphaCodium | 2024 |
| 21 | Prompt DSL | Orchestration | APPL/PDL | 2024 |
| 22 | Multi-Agent Design | Orchestration | MASS | 2025 |
| 23 | Auto-Optimization | Optimization | APO/GEPA | 2023→2025 |
| 24 | Prompt Compression | Optimization | LLMLingua | 2023→2024 |
| 25 | Prompt Rewriting | Optimization | RL rewrite | 2024 |
| 26 | Prompt + Fine-Tuning | Optimization | BetterTogether | 2024 |
| 27 | Self-Supervised Optimization | Optimization | SPO | 2025 |
| 28 | Soft Prompt Tuning | Optimization | LoPA | 2024 |
| 29 | Bias Calibration | Quality | Debiasing | 2024 |
| 30 | Sensitivity Assessment | Quality | POSIX | 2023→2025 |
| 31 | Perturbation Consistency | Quality | PPCL | 2024 |
| 32 | LLM-as-Judge | Quality | Eval templates | 2024 |
| 33 | Domain-Specific | Quality | Medical/SQL/Multilingual | 2023→2024 |

## 🟢 Defense Techniques

| # | Technique | Category | Core Keywords | Year |
|---|------|------|-----------|------|
| 34 | Spotlighting | Defense | Data marking | 2024 |
| 35 | Structured Separation | Defense | StruQ | 2024 |
| 36 | Preference-Based Defense | Defense | SecAlign | 2024→2025 |
| 37 | Injection Detection | Defense | PromptArmor | 2025 |
| 38 | Architecture-Level Immunity | Defense | CaMeL | 2025 |
| 39 | Multi-Agent Security | Defense | MELON | 2025 |
| 40 | Theft Protection | Defense | PromptKeeper | 2024 |
| 41 | Unlearning & Caching | Defense/System | ECO/Preble | 2024 |

## 🔴 Attack Techniques (Security Research Only)

| # | Technique | Category | Core Keywords | Year |
|---|------|------|-----------|------|
| 42 | Indirect Injection Attack | Attack | HouYi | 2023 |
| 43 | Manual Jailbreak Templates | Attack | DAN | 2023 |
| 44 | Automated Jailbreak | Attack | AutoDAN/GPTFUZZER | 2023→2024 |
| 45 | Decomposition Attack | Attack | DrAttack | 2024 |
| 46 | Sequential Chain Attack | Attack | SequentialBreak | 2024 |
| 47 | Prompt Stealing | Attack | output2prompt/PLeak | 2024 |
| 48 | Learned Triggers | Attack | Neural Exec | 2024 |
| 49 | Adaptive Attacks | Attack | Defense bypass | 2025 |
| 50 | Injection Formalization | Attack/Benchmark | Unified framework | 2023→2025 |

---

# Appendix: Data Sources

| Field | Count |
|------|------|
| Search Scope | arXiv 2023–2026 CS categories, title contains "prompt" |
| Total Matched Papers | 5,366 |
| After Deduplication | 5,362 |
| After Filtering (AI/LLM prompt-related) | 4,780 |
| Removed (Vision/Speech/Graph/Non-LLM) | 582 |
| Core Classification Coverage | 50 techniques (8 categories) |

> This document was systematically compiled from the abstracts of 4,780 papers. All sources are annotated with arXiv IDs for direct reference.
