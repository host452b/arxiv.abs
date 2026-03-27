# arxiv.agent-skills — AI Agent 技能技术全景

**2606 篇 arXiv 摘要**，来自 CS 类别 14 个主题搜索，覆盖 AI Agent 核心技能技术的系统性研究。

**核心问题：** Agent 的哪些技能组合，能以最小工程成本实现最大任务能力提升？

## 搜索主题

| # | 技能类别 | 关键词 | 论文数 | 结果文件 | 被推翻的理论 / 既定谬误 |
|---|---------|--------|--------|-------------|
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

```
优先级 1 — 推理框架（ReAct/CoT）
  推理-行动交织是所有 Agent 任务的基础杠杆
  ALFWorld: +34% | WebShop: +10% vs 纯 RL

优先级 2 — 工作流记忆（AWM）
  归纳可复用流程，减少每次从零探索
  Mind2Web: +24.6% | WebArena: +51.1%

优先级 3 — ACI 接口设计（SWE-agent 范式）
  为 Agent 构建专用接口，而非使用人类界面
  SWE-bench: 12.5%（SOTA）| HumanEvalFix: 87.7%
```

### 最大开放差距

```
GUI 接地鸿沟：人类 72.36% vs AI 12.24%（差距 6x）
→ OSWorld 基准，369 个真实计算机任务
→ 瓶颈：视觉接地 + 操作知识，而非推理规划
→ 语言层面的 Agent 能力不能直接迁移到视觉操作
```

### 安全核心张力

多 Agent 系统暴露两个对立失败模式：
- **幻觉级联**：单步错误在多 Agent 链中放大（MetaGPT 的 SOP 设计就是为了解决此问题）
- **过约束失能**：过多安全检查会大幅降低任务成功率

> 目前没有既安全又高性能的通用 Agent 安全方案——这是该领域最大的工程开放问题。

---

## 摘要文件（按年份）

| 年份 | 论文数 | 目录 |
|------|--------|------|
| 2000 | 1 | [2000/abstracts/](2000/abstracts/) | — |
| 2008–2017 | 57 | 2008–2017/abstracts/ |
| 2018 | 35 | [2018/abstracts/](2018/abstracts/) | — |
| 2019 | 54 | [2019/abstracts/](2019/abstracts/) | — |
| 2020 | 79 | [2020/abstracts/](2020/abstracts/) | — |
| 2021 | 92 | [2021/abstracts/](2021/abstracts/) | — |
| 2022 | 98 | [2022/abstracts/](2022/abstracts/) | — |
| 2023 | 179 | [2023/abstracts/](2023/abstracts/) | — |
| 2024 | 450 | [2024/abstracts/](2024/abstracts/) | — |
| 2025 | 1117 | [2025/abstracts/](2025/abstracts/) | — |
| 2026 | 442 | [2026/abstracts/](2026/abstracts/) | — |

## 搜索参数

- 类别：`cs`（计算机科学）
- 排序：`relevance`（相关度优先）
- 工具：[arxs](https://github.com/host452b/arxs) v1.0.3

---

## 各类别 80/20 最佳实践

> **二八定律：** 每个技能领域中，20% 的关键实践驱动 80% 的能力提升。下列关键杠杆均来自该类别论文的高频共识。

### 01 推理技能

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **ReAct（推理 + 行动）**：在行动步骤中交织显式推理轨迹 | ALFWorld +34% / WebShop +10% vs 纯 RL；是所有 Agent 任务类型的基础杠杆 |
| **思维链（CoT）**：在回答前强制逐步推理 | 在数学、逻辑、多步问答上持续提升；代价仅是提示 token |

> ReAct 结构化"思考-行动"，CoT 结构化"推理过程"——两者共同覆盖 80% 的 Agent 推理质量提升。

---

### 02 记忆技能

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **工作流记忆（AWM）**：从历史任务中归纳可复用流程 | Mind2Web +24.6% / WebArena +51.1%；消除重复任务中的冗余探索 |
| **上下文工作记忆**：在活跃上下文窗口内进行结构化状态追踪 | 无需外部存储即可实现多步任务连贯性；覆盖 80% 的短程记忆需求 |

> 工作流记忆管长期复用，工作记忆管当次状态——两者覆盖 80% 的 Agent 记忆需求。

---

### 03 工具调用

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **结构化函数调用**（JSON Schema / 类型化接口） | 稳定、可解析的工具调用；消除自由文本解析失败——这是大多数工具调用错误的根源 |
| **工具路由 / 选择**：将任务类别匹配到正确工具 | 工具选择正确与否决定任务是否可解；工具选错 = 必然失败 |

> 可靠调用 + 正确选择，共同覆盖 80% 的工具调用工程失败。

---

### 04 任务规划

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **层次化任务分解**：目标 → 子目标 → 行动 | 防止上下文过载，支持并行子目标执行；长程规划论文的主导模式 |
| **先规划再执行 + 重规划**：生成计划、执行、检测失败、修订 | 处理大多数来自中间状态意外的任务失败 |

> 分解降低复杂度，重规划处理现实偏差——两者共同覆盖 80% 的规划任务成功率。

---

### 05 多 Agent 协作

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **角色专业化**：每个 Agent 有清晰边界的领域/技能 | 减少幻觉级联；MetaGPT 的 SOP 设计验证：角色清晰是多 Agent 系统最大的质量杠杆 |
| **结构化通信协议**：Agent 之间类型化消息传递 | 防止错误在 Agent 链中放大；非结构化通信是大多数多 Agent 协调失败的根本原因 |

> 角色清晰 + 结构化消息，共同覆盖 80% 的多 Agent 协调质量问题。

---

### 06 代码 Agent

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **Agent-Computer Interface（ACI）设计**：为 Agent 构建专用接口，而非使用人类界面 | ACI 设计决定能力上限；SWE-bench 12.5%（SOTA）/ HumanEvalFix 87.7% 验证这是第一杠杆 |
| **迭代反馈循环**：运行 → 观察输出 → 诊断 → 修复 | 覆盖约 80% 可从执行输出中检测到的编程错误 |

> ACI 定义 Agent 能感知和操作的范围；迭代反馈覆盖大多数可修复错误——两者共同决定并逼近能力上限。

---

### 07 RAG / 检索增强

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **稠密向量检索**（基于嵌入的语义搜索） | 在改写和语义变体上超越关键词检索；大多数 RAG Agent 系统的默认检索骨干 |
| **Self-RAG（自适应检索）**：只在需要时检索，并自我评估检索质量 | 在 QA/推理/事实性上超越 ChatGPT；避免过度检索引入的噪声 |

> 稠密检索提供质量，自适应触发防止噪声——两者共同覆盖 80% 的 RAG Agent 性能提升。

---

### 08 Agent 评测

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **真实任务基准测试**：真实浏览器 / 操作系统 / 代码环境，而非合成任务 | 揭示真实能力差距；OSWorld 人类 72% vs AI 12% 的差距在合成基准中不可见 |
| **多指标评估**：成功率 + 步骤效率 + 安全违规 | 单指标（仅成功率）掩盖 80% 的失败模式多样性 |

> 真实环境揭示真实差距，多指标捕获失败多样性——两者共同覆盖 80% 的有效评测信号。

---

### 09 Agent 安全

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **沙箱执行环境**：将 Agent 行动与生产系统隔离 | 防止灾难性不可逆行动；是任何部署 Agent 的最小有效安全边界 |
| **输出过滤 + 行动白名单**：将行动空间限制在预批准操作范围内 | 无需 Agent 自行推理安全性即可阻断大多数有害输出 |

> 沙箱控制爆炸半径，白名单约束攻击面——两者覆盖 80% 的实际 Agent 安全需求，但目前尚无兼顾安全与高性能的通用方案。

---

### 10 具身 AI

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **闭环感知-行动**（观察 → 行动 → 观察反馈） | 物理任务成功的基础前提；开环执行在任何真实物理变化下均失败 |
| **技能原语库**（Voyager 范式）：可复用的行动构建块 | 3.3× 物品 / 15.3× 里程碑；在一个情境学到的技能可迁移到新任务——能力持续复利 |

> 闭环反馈处理现实，技能库复利能力——两者共同覆盖 80% 的具身 Agent 性能。

---

### 11 Agent 架构

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **LLM 作为控制器 + 模块化工具**：LLM 负责推理，独立模块负责记忆/规划/工具 | 大多数 Agent 系统的主导架构模式；分离使各模块可独立改进 |
| **上下文管理策略**：决定保留、总结还是卸载到外部存储 | 上下文窗口管理是隐性瓶颈；此处失败导致大多数长任务连贯性崩溃 |

> 模块化架构实现灵活性，上下文策略实现连贯性——两者共同覆盖 80% 的 Agent 架构设计决策。

---

### 12 自我改进

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **结构化自我反思**：在提出修复方案前先识别具体错误类型 | 随机重试失败；结构化诊断"为什么失败"驱动大多数迭代改进收益 |
| **反馈驱动的迭代精炼**：用执行输出 / 评判信号作为精炼输入 | 自我改进系统的核心循环；覆盖编程、写作、推理和规划任务 |

> 先诊断再修复 + 执行反馈作为信号——两者共同覆盖 80% 的 Agent 类型自我改进收益。

---

### 13 角色扮演

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **通过系统提示维持角色一致性**：在系统提示中定义角色知识、语气和边界 | 角色一致性最有效的单一杠杆；覆盖 80% 的角色扮演质量问题 |
| **知识边界约束**：角色只了解其在世界中应该了解的信息 | 防止破坏沉浸感的时代错误和幻觉；是角色扮演 Agent 第二大失败模式 |

> 角色定义 + 知识边界——两者共同覆盖 80% 的角色扮演角色质量问题。

---

### 14 长程任务

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **带显式检查点的子目标分解**：将长任务分解为可验证的里程碑 | 大多数长程任务失败发生在子目标边界；显式检查点在失败传播前捕获它 |
| **状态持久化与恢复**：在每个检查点保存任务状态，从最后成功处恢复 | 避免从零重启百步任务；覆盖 80% 的长程任务可靠性需求 |

> 子目标分解 + 检查点恢复——两者共同覆盖 80% 的长程任务工程挑战。

---

[English README](README.md) | [返回主目录](../README.md)

---

## Paradigm Shifts / 范式转移 (Kuhn)

```
OLD PARADIGM                    Trigger Event                   NEW PARADIGM
─────────────────────          ─────────────────────          ─────────────────────
LLMs are text generators only   ReAct / tool calling (2022)   Tool-using reasoning agents
  │ text in → text out               │ thought-action-observation    │ agents act in environment
  └──────────────────────────────── ┘
```

**已被推翻的认知误区:**
- ✗ "LLM无法进行形式推理" → CoT和草稿本提示使多步逻辑推理成为可能
- ✗ "Transformer无法拥有持久记忆" → 外部记忆存储（RAG）赋予LLM超越上下文窗口的记忆
- ✗ "RAG消除LLM幻觉" → RAG将问题转移到检索质量

