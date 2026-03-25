# arxiv.agent-skills — AI Agent 技能技术全景

**2606 篇 arXiv 摘要**，来自 CS 类别 14 个主题搜索，覆盖 AI Agent 核心技能技术的系统性研究。

**核心问题：** Agent 的哪些技能组合，能以最小工程成本实现最大任务能力提升？

## 搜索主题

| # | 技能类别 | 关键词 | 论文数 | 结果文件 |
|---|---------|--------|--------|----------|
| 01 | 推理技能 | chain of thought / tree of thought / ReAct / self reflection | 200 | [01-reasoning.json](search-results/01-reasoning.json) |
| 02 | 记忆技能 | agent memory / episodic memory / working memory / memory augmented | 200 | [02-memory.json](search-results/02-memory.json) |
| 03 | 工具调用 | tool use / function calling / tool augmented / API agent / tool learning | 200 | [03-tool-use.json](search-results/03-tool-use.json) |
| 04 | 任务规划 | task planning / task decomposition / hierarchical planning / goal decomposition | 200 | [04-planning.json](search-results/04-planning.json) |
| 05 | 多 Agent 协作 | multi agent / multiagent cooperation / agent coordination / agent collaboration | 200 | [05-multiagent.json](search-results/05-multiagent.json) |
| 06 | 代码 Agent | code agent / software agent / coding agent / SWE agent / autonomous coding | 200 | [06-code-agents.json](search-results/06-code-agents.json) |
| 07 | RAG / 检索增强 | retrieval augmented agent / knowledge retrieval agent / RAG agent | 200 | [07-rag-retrieval.json](search-results/07-rag-retrieval.json) |
| 08 | Agent 评测 | agent benchmark / agent evaluation / LLM agent benchmark | 200 | [08-agent-eval.json](search-results/08-agent-eval.json) |
| 09 | Agent 安全 | agent safety / agent alignment / agent oversight / LLM agent attack | 200 | [09-agent-safety.json](search-results/09-agent-safety.json) |
| 10 | 具身 AI | embodied agent / embodied AI / grounded agent / physical agent | 200 | [10-embodied.json](search-results/10-embodied.json) |
| 11 | Agent 架构 | LLM agent / autonomous agent architecture / agentic framework | 200 | [11-agent-arch.json](search-results/11-agent-arch.json) |
| 12 | 自我改进 | self improvement agent / self refinement / self correction / iterative refinement | 200 | [12-self-improve.json](search-results/12-self-improve.json) |
| 13 | 角色扮演 | role playing agent / persona agent / character simulation / roleplay LLM | 116 | [13-roleplay.json](search-results/13-roleplay.json) |
| 14 | 长程任务 | long horizon agent / autonomous agent task / web agent / computer agent | 200 | [14-long-horizon.json](search-results/14-long-horizon.json) |

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

## 摘要文件

- [`abstracts/`](abstracts/) — 2606 个 `.txt` 文件（标题、作者、arXiv ID、URL、摘要）

## 搜索参数

- 类别：`cs`（计算机科学）
- 排序：`relevance`（相关度优先）
- 工具：[arxs](https://github.com/host452b/arxs) v1.0.3

---

[English README](README.md) | [返回主目录](../README.md)
