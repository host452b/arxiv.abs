# arxiv.agent-harness

覆盖 **LLM 驱动智能体系统**全生命周期的 arXiv 论文集合：
框架与编排、规划、工具调用、记忆管理、多 Agent 协调、
评测基准、安全护栏、代码 Agent、浏览器/GUI Agent 以及生产可靠性。

- **时间范围**：2020–2026（AI Agent 时代聚焦）
- **去重论文总量**：2,177 篇
- **检索文件**：42 个主题搜索
- **年份分布**：2020(49) · 2021(55) · 2022(80) · 2023(198) · 2024(482) · 2025(949) · 2026(339)

---

## 搜索主题（42 个检索）

| 编号 | 主题 | 文件 |
|------|------|------|
| 01 | Agent 框架与编排 | `01-agent-framework.json` |
| 02 | AutoGen / LangChain / CrewAI | `02-autogen-langchain.json` |
| 03 | Agentic 工作流与流水线 | `03-agentic-workflow.json` |
| 04 | LLM Agent（通用） | `04-llm-agent.json` |
| 05 | ReAct：推理+行动 | `05-react-agent.json` |
| 06 | 思维链+工具调用 | `06-chain-of-thought-act.json` |
| 07 | 思维树/思维图 | `07-tree-of-thought.json` |
| 08 | Agent 规划与任务规划 | `08-agent-planning.json` |
| 09 | 自我反思与自我批评 | `09-self-reflection.json` |
| 10 | Agent 推理与决策 | `10-agent-reasoning.json` |
| 11 | LLM 工具使用 | `11-tool-use-llm.json` |
| 12 | 函数调用 / API 调用 | `12-function-calling.json` |
| 13 | 工具选择与学习 | `13-tool-selection.json` |
| 14 | Agent 记忆与情节记忆 | `14-agent-memory.json` |
| 15 | 长上下文 Agent | `15-long-context.json` |
| 16 | 记忆模块与 Agent 状态 | `16-memory-module.json` |
| 17 | 多 Agent + LLM | `17-multi-agent-llm.json` |
| 18 | Agent 通信与协调 | `18-agent-communication.json` |
| 19 | 角色扮演 Agent 与人设 | `19-role-playing-agent.json` |
| 20 | Agent 社会 | `20-society-agents.json` |
| 21 | Agent 基准测试与评测 | `21-agent-benchmark.json` |
| 22 | Agent 能力与性能 | `22-agent-capability.json` |
| 23 | 自主 Agent 评测 | `23-agentic-eval.json` |
| 24 | Agent 安全与对齐 | `24-agent-safety.json` |
| 25 | Agent 护栏与约束 | `25-agent-guardrail.json` |
| 26 | Agent 红队测试 | `26-red-teaming-agent.json` |
| 27 | Agent 沙箱与隔离 | `27-agent-sandbox.json` |
| 28 | 代码 Agent / 编程 Agent | `28-code-agent.json` |
| 29 | SWE-Agent / 软件工程 Agent | `29-swe-agent.json` |
| 30 | 自主编程与 AI 程序员 | `30-autonomous-coding.json` |
| 31 | 仓库 / 代码库 Agent | `31-repo-agent.json` |
| 32 | Web Agent / 浏览器 Agent | `32-web-agent.json` |
| 33 | 计算机使用 & GUI Agent | `33-computer-use.json` |
| 34 | Web 导航与浏览 | `34-web-navigation.json` |
| 35 | RAG + Agent | `35-rag-agent.json` |
| 36 | 知识检索 Agent | `36-knowledge-agent.json` |
| 37 | 长程任务 Agent | `37-long-horizon.json` |
| 38 | Agent 可靠性与鲁棒性 | `38-agent-reliability.json` |
| 39 | Agent 测试与调试 | `39-agent-testing.json` |
| 40 | 人机协同 Agent | `40-human-loop-agent.json` |
| 41 | Agent 监控与可观测性 | `41-agent-monitoring.json` |
| 42 | 评测框架与 Agent Harness | `42-agent-eval-harness.json` |

---

## 分类分析（12 大簇）

### A01 · Agent 框架与编排 — 139 篇

构建 Agent 系统的核心基础设施。

| 子主题 | 数量 | 关键内容 |
|--------|------|----------|
| 框架设计（LangChain、AutoGen、CrewAI） | ~55 | 多框架对比、设计模式 |
| 编排与流水线 | ~45 | 任务分解、Agent 链路 |
| 通用 Agentic 工作流 | ~39 | 流水线自动化、Agent 即服务 |

**80/20 核心**：约 30 篇框架设计与 LLM 编排论文覆盖大部分工程知识，
重点关注架构对比与故障模式研究。

---

### A02 · 规划与推理 — 104 篇

Agent 如何规划多步任务并在行动前推理。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| ReAct（推理+行动） | ~35 | ReAct 原始论文及扩展版本 |
| 思维树/思维图 | ~28 | ToT、GoT、广度优先规划 |
| 自我反思与批评 | ~25 | Reflexion、迭代精化 |
| 任务规划 | ~16 | 层次规划、子目标生成 |

**80/20 核心**：ReAct 与 Tree-of-Thought 变体构成主流范式，约 25 篇论文
覆盖生产级 Agent 的基本规划原语。

---

### A03 · 工具使用与函数调用 — 77 篇

通过工具调用将 Agent 锚定到真实世界动作。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| LLM 工具使用 | ~35 | Toolformer、ToolBench、API 基础 |
| 函数调用 | ~25 | OpenAI 函数调用风格、schema 设计 |
| 工具选择与学习 | ~17 | 何时选择何种工具 |

**80/20 核心**：约 15 篇函数调用范式与工具选择策略论文覆盖生产实现。

---

### A04 · 记忆与上下文管理 — 32 篇

超越上下文窗口的持久记忆。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| Agent 记忆系统 | ~18 | MemGPT、情节记忆+语义记忆 |
| 长上下文 Agent | ~9 | RAG vs 长上下文、检索增强 Agent |
| 记忆模块 | ~5 | 外部记忆存储、向量数据库集成 |

**80/20 核心**：MemGPT 风格的记忆增强 + 检索策略约 10 篇论文构成实践基础。

---

### A05 · 多 Agent 系统 — 412 篇 ⭐（最大簇）

多个 LLM Agent 之间的协调、通信和涌现行为。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| 通用多 Agent LLM | ~180 | 协调协议、Agent 社会 |
| Agent 通信与协商 | ~100 | 消息传递、对话协议 |
| 角色扮演与人设 | ~70 | 专业化角色、Agent 差异化 |
| Agent 社会 | ~62 | 涌现行为、Agent 生态系统 |

**80/20 核心**：约 80 篇多 Agent 通信协议与角色分工论文覆盖主要研究模式。
ChatDev、MetaGPT 等社会级论文被引用最多。

---

### A06 · Agent 基准测试与评测 — 66 篇

衡量 Agent 能力边界的方法与框架。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| Agent 基准测试套件 | ~30 | WebArena、AgentBench、GAIA、SWE-bench |
| 能力评估 | ~22 | 任务完成率、错误分析 |
| 自主 Agent 基准 | ~14 | Agentic 评测 vs 静态评测 |

**80/20 核心**：约 15 篇广泛引用的基准论文（SWE-bench、WebArena、AgentBench）
定义了评测格局。

---

### A07 · Agent 安全与护栏 — 18 篇

防止有害或意外的 Agent 行为。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| Agent 安全/对齐 | ~10 | 规格博弈、目标泛化失败 |
| 护栏与约束 | ~5 | 硬约束、动作过滤 |
| 沙箱与隔离 | ~3 | 容器级隔离 |

**80/20 核心**：这是一个小但关键的簇。约 8 篇 Agent 专属安全论文（区别于
通用 LLM 安全）是基础性工作。

---

### A08 · 代码与软件工程 Agent — 109 篇

编写、调试和修改代码的 AI Agent。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| 通用代码 Agent | ~45 | CodeAct、OpenDevin、Aider、Cursor |
| SWE-Agent 修复 Bug | ~35 | GitHub Issue 解决、PR 生成 |
| 自主编程 | ~20 | AI 程序员、无脚手架编程 |
| 仓库/代码库 Agent | ~9 | 全仓库理解、多文件编辑 |

**80/20 核心**：SWE-bench + SWE-agent + 10 篇代码 Agent 框架论文覆盖构建
编程 Agent 的约 80% 实践知识。

---

### A09 · Web 与计算机使用 Agent — 200 篇

导航浏览器、GUI 和 Web 环境的 Agent。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| Web Agent / 浏览器 Agent | ~80 | WebGPT、WebAgent、Mind2Web |
| 计算机使用 & GUI Agent | ~70 | Claude Computer Use、AppAgent、UI 定位 |
| Web 导航 | ~50 | DOM 操作、基于截图的导航 |

**80/20 核心**：约 40 篇 GUI/Web 定位与导航策略论文。计算机使用论文在
2024–2025 年急速增长。

---

### A10 · RAG 与知识 Agent — 590 篇 ⭐（第二大簇）

检索增强生成作为 Agent 核心能力。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| RAG + Agent 集成 | ~280 | Agentic RAG、迭代检索 |
| 知识检索 Agent | ~180 | 知识图谱集成、结构化知识 |
| 检索策略 | ~130 | 稠密检索、重排序 |

**80/20 核心**：RAG 原始论文 + 约 50 篇 Agentic RAG 变体覆盖核心模式。
迭代/自问检索是当前前沿。

---

### A11 · 长程任务与可靠性 — 94 篇

在长时任务中保持正确行为。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| 长程任务 | ~50 | 多日任务、持久状态 |
| Agent 可靠性与鲁棒性 | ~25 | 错误恢复、重试策略 |
| Agent 测试与调试 | ~19 | 自动化测试、轨迹分析 |

**80/20 核心**：约 20 篇长程任务分解与故障恢复论文覆盖 Agent 可靠性
工程的核心内容。

---

### A12 · 人机协同与可观测性 — 28 篇

保持人类知情权与控制权。

| 子主题 | 数量 | 代表论文 |
|--------|------|----------|
| 人机协同（HITL） | ~15 | 审批工作流、HITL 设计模式 |
| Agent 监控与可观测性 | ~8 | 轨迹日志、异常检测 |
| 评测框架 | ~5 | Agent 的 CI/CD、回归测试 |

**80/20 核心**：约 10 篇 HITL 设计模式与 Agent 可观测性论文是生产部署
的基础。

---

## 横向发现

1. **2024–2025 加速**：68% 的论文发表于这两年，反映了 GPT-4 和 Claude 3
   发布后以 Agent 为中心的研究爆发。

2. **多 Agent 主导**：A05（412 篇）和 A10/RAG（590 篇）是最大两个簇，
   表明多 Agent 协调与检索增强是核心研究主题。

3. **软件 Agent 作为旗舰基准**：A08 代码 Agent 以 SWE-bench 为统一评测标准
   ——迄今最具影响力的 Agent 基准测试。

4. **安全研究严重不足**：A07 仅 18 篇，相对于 Agent 的部署规模严重偏少
   ——这是一个关键研究空白。

5. **GUI/计算机使用高速增长**：A09 从 2023 到 2025 年增长 5 倍，由
   Claude Computer Use、GPT-4V 及开源 GUI Agent 框架驱动。

---

## arXiv 分类分布

| 分类 | 论文数 | 研究方向 |
|------|--------|----------|
| cs.AI | 480 | 人工智能（通用 Agent 架构） |
| cs.CL | 465 | 计算与语言（LLM 驱动的 Agent） |
| cs.LG | 194 | 机器学习（基于学习的 Agent 组件） |
| cs.SE | 190 | 软件工程（编码 Agent、SWE-bench） |
| cs.CR | 114 | 密码学与安全（Agent 安全、红队） |
| cs.CV | 84 | 计算机视觉（GUI/视觉 Agent） |

---

[English README](README.md) | [知识文档](agent-harness.md) | [返回主目录](../README.md)
