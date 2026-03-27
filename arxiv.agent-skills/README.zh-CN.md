# arxiv.agent-skills — AI Agent 技能技术全景

**2606 篇 arXiv 摘要**，来自 CS 类别 14 个主题搜索，覆盖 AI Agent 核心技能技术的系统性研究。

**核心问题：** Agent 的哪些技能组合，能以最小工程成本实现最大任务能力提升？

## 搜索主题

| # | 技能类别 | 关键词 | 论文数 | 结果文件 | 被推翻的理论 / 既定谬误 |
|---|---|---|---|---|---|
| 01 | 推理技能 | chain of thought / tree of thought / ReAct / self reflection | 200 | [01-reasoning.json](search-results/01-reasoning.json) | "LLMs cannot do formal reasoning" → Chain-of-thought and scratchpad prompting enable multi-step logical and mathematical reasoning beyond what was thought possible at scale. |
| 02 | 记忆技能 | agent memory / episodic memory / working memory / memory augmented | 200 | [02-memory.json](search-results/02-memory.json) | "Transformers cannot have persistent memory" → External memory stores (RAG, episodic memory modules) give LLM agents indefinite effective memory beyond context window limits. |
| 03 | 工具调用 | tool use / function calling / tool augmented / API agent / tool learning | 200 | [03-tool-use.json](search-results/03-tool-use.json) | "LLMs cannot reliably use external tools" → ReAct and function-calling have made reliable tool use mainstream; the original 'LLMs can only generate text' assumption is obsolete. |
| 04 | 任务规划 | task planning / task decomposition / hierarchical planning / goal decomposition | 200 | [04-planning.json](search-results/04-planning.json) | "LLMs cannot plan multi-step tasks" → LLM-based planners (HuggingGPT, ToT) demonstrate multi-step task decomposition; the claim they 'cannot plan' is too strong. |
| 05 | 多 Agent 协作 | multi agent / multiagent cooperation / agent coordination / agent collaboration | 200 | [05-multiagent.json](search-results/05-multiagent.json) | "Multi-agent systems always outperform single agents" → Without coordination protocols and consensus mechanisms, multi-agent debates can amplify errors. |
| 06 | 代码 Agent | code agent / software agent / coding agent / SWE agent / autonomous coding | 200 | [06-code-agents.json](search-results/06-code-agents.json) | "Code generation requires specialized training on code" → General-purpose LLMs generalize to code through in-context learning. |
| 07 | RAG / 检索增强 | retrieval augmented agent / knowledge retrieval agent / RAG agent | 200 | [07-rag-retrieval.json](search-results/07-rag-retrieval.json) | "RAG eliminates LLM hallucination" → RAG shifts the problem to retrieval quality; 'garbage in, garbage out'. |
| 08 | Agent 评测 | agent benchmark / agent evaluation / LLM agent benchmark | 200 | [08-agent-eval.json](search-results/08-agent-eval.json) | "Human evaluation is the gold standard for agents" → Human evaluation is expensive, inconsistent, and slow; calibrated LLM-as-judge achieves comparable correlation at scale. |
| 09 | Agent 安全 | agent safety / agent alignment / agent oversight / LLM agent attack | 200 | [09-agent-safety.json](search-results/09-agent-safety.json) | "Safety-trained agents are safe in all contexts" → Safety is brittle under distribution shift; agents safe in training can exhibit unsafe behavior in novel contexts. |
| 10 | 具身 AI | embodied agent / embodied AI / grounded agent / physical agent | 200 | [10-embodied.json](search-results/10-embodied.json) | "Robot intelligence requires hand-engineered control loops" → Foundation models (RT-2, π0) transfer internet-scale knowledge to robotic manipulation. |
| 11 | Agent 架构 | LLM agent / autonomous agent architecture / agentic framework | 200 | [11-agent-arch.json](search-results/11-agent-arch.json) | "Transformer architecture is sufficient for AGI" → Memory bandwidth, energy efficiency, and compositional generalization challenges motivate architectural innovation. |
| 12 | 自我改进 | self improvement agent / self refinement / self correction / iterative refinement | 200 | [12-self-improve.json](search-results/12-self-improve.json) | "Self-improvement leads to intelligence explosion" → Practical self-improvement is constrained by search costs and objective specification. |
| 13 | 角色扮演 | role playing agent / persona agent / character simulation / roleplay LLM | 116 | [13-roleplay.json](search-results/13-roleplay.json) | "Role-playing is benign and just a creative feature" → Role-playing is a documented jailbreak vector; constitutional constraints must persist through persona adoption. |
| 14 | 长程任务 | long horizon agent / autonomous agent task / web agent / computer agent | 200 | [14-long-horizon.json](search-results/14-long-horizon.json) | "Long-horizon agents just need more context" → Context window scaling doesn't solve coherence decay; planning, state tracking, and re-planning are separate requirements. |

**原始结果 2716 篇 → 去重后 2606 篇摘要**

## 核心发现摘要

> 详细分析见 [agent-skills-findings.zh-CN.md](agent-skills-findings.zh-CN.md)

### 关键定量数据（来自摘要采样）

| 数据 | 来源论文 | 意义 |
|------|---------|------|
| **ALFWorld +34% / WebShop +10%** | Yao et al. 2022, [arXiv:2210.03629](https://arxiv.org/abs/2210.03629) | ReAct 推理-行动框架 vs 纯 RL 基线 |
| **3.3x 物品 / 15.3x 里程碑** | Wang et al. 2023, [arXiv:2305.16291](https://arxiv.org/abs/2305.16291) | Voyager 技能库使具身 Agent 持续加速 |
| **SWE-bench 12.5% / HumanEvalFix 87.7%** | Yang et al. 2024, [arXiv:2405.15793](https://arxiv.org/abs/2405.15793) | ACI 接口设计决定代码 Agent 能力上限 |
| **人类 72.36% vs AI 12.24%** | Xie et al. 2024, [arXiv:2404.07972](https://arxiv.org/abs/2404.07972) | OSWorld GUI 接地是最大未解差距 |
| **Mind2Web +24.6% / WebArena +51.1%** | Wang et al. 2024, [arXiv:2409.07429](https://arxiv.org/abs/2409.07429) | Agent 工作流记忆的收益区间 |
| **超越 ChatGPT（QA / 推理 / 事实）** | Asai et al. 2023, [arXiv:2310.11511](https://arxiv.org/abs/2310.11511) | Self-RAG 自适应检索优于固定检索 |

### 技能 × 工程目标矩阵

> ✅ 强证据；⭕ 部分证据；⬜ 待研究

| 技能类型 | 推理质量 | 任务完成率 | 上下文管理 | 多步规划 | 真实接地 | 安全可控 |
|---------|---------|----------|----------|---------|---------|---------|
| **推理（CoT/ReAct）** | ✅ | ✅ | ⭕ | ✅ | ⭕ | ⬜ |
| **记忆（工作流/情节）** | ⭕ | ✅ | ✅ | ✅ | ⭕ | ⬜ |
| **工具调用** | ⭕ | ✅ | ⬜ | ⭕ | ✅ | ⭕ |
| **任务规划** | ✅ | ✅ | ⭕ | ✅ | ⬜ | ⬜ |
| **多 Agent 协作** | ⭕ | ✅ | ⭕ | ✅ | ⬜ | ⭕ |
| **代码 Agent** | ⭕ | ✅ | ⭕ | ✅ | ✅ | ⭕ |
| **RAG/检索增强** | ✅ | ✅ | ✅ | ⬜ | ⭕ | ⭕ |
| **自我改进/反思** | ✅ | ✅ | ⭕ | ⭕ | ⬜ | ⭕ |
| **具身 AI** | ⬜ | ⭕ | ⬜ | ⭕ | ✅ | ⭕ |

### 核心结论（Pareto 20/80）

**20% 技能驱动 80% 能力提升：**

| 旧范式 | 触发事件 | 新范式 |
|---|---|---|
| **LLM 只是文本生成器** — 文本进，文本出 | ReAct / 工具调用 (2022): 思考-行动-观察 | **工具型推理 Agent** — Agent 在真实环境中执行操作 |
| **每个任务单独微调** — 每项技能训练一个专用模型 | GPT-4 泛化能力 (2023): 上下文内技能学习 | **具备技能迁移的通用 Agent** — 一个 Agent，覆盖多个领域 |
| **人类介入是瓶颈** — 人类拖慢了所有流程 | HITL 研究 (2023+): 审批门控显著提升输出质量 | **人类介入是质量倍增器** — 有效监督带来更好结果 |

**已被推翻的认知误区:**
- ✗ "LLM无法进行形式推理" → CoT和草稿本提示使多步逻辑推理成为可能
- ✗ "Transformer无法拥有持久记忆" → 外部记忆存储（RAG）赋予LLM超越上下文窗口的记忆
- ✗ "RAG消除LLM幻觉" → RAG将问题转移到检索质量


---

## 公认谬误 / Established Fallacies

| 误解 | 为何盛行 | 实证结论 |
|---|---|---|
| LLM 能可靠地进行形式数学运算 | GSM8K 和 MATH 基准得分很高 | 换一种表述方式后，模型对等价问题会失败；模式匹配 ≠ 数学推理（Mirzadeh 等，2024） |
| 上下文示例越多，性能越好 | 直觉：展示越多 → 学到越多 | 随机示例可使性能下降 15% 以上；通过检索选择的示例优于随机选择（Liu 等，2022） |
| 技能涌现可以从规模预测 | 基于平滑缩放定律外推 | 技能涌现是非连续的且与模型系列相关，无法单纯从损失曲线预测 |

## 过时科学理论 / Obsolete Scientific Theories

| 理论 | 流行年代 | 被取代原因 |
|---|---|---|
| 专家系统用于技能编码（MYCIN, XCON） | 1980s–1990s | 在边缘案例上过于脆弱；维护成本极高；已被微调和提示的 LLM 取代 |
| 基于案例的推理（CBR）作为技能基础 | 1990s–2000s | 在案例库范围外泛化能力差；已被神经检索 + LLM 适配取代 |
| 符号定理证明器用于代码生成 | 1970s–2000s | 交互响应太慢；LLM 代码生成（Codex, Claude, Copilot）现已占主导 |

## 被证伪的理论 / Falsified Theories

| 理论 | 核心预测 | 证伪证据 |
|---|---|---|
| 多 Agent 辩论总能提升准确率 | 预测：Agent 间分歧能纠正个体错误 | Du 等（2023）及后续研究：多数错误的情况被辩论放大；需要外部验证器 |
| RAG 消除知识截止日期限制 | 预测：检索 = 始终是最新知识 | 当查询-文档语义匹配较高但内容有误时，RAG 会自信地检索错误块；幻觉转移而非消除 |
