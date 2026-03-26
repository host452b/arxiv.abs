# Agent Harness — Knowledge Document

> 基于 2,177 篇论文摘要（2020–2026）提炼的 LLM Agent 工程知识体系

---

## 一、Agent 系统核心架构

### 1.1 Agent 的四大基础模块

现代 LLM Agent 系统由四个相互依赖的模块构成：

```
┌─────────────────────────────────────────────┐
│                  LLM Agent                  │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │  规划器   │  │  记忆库   │  │  工具集   │  │
│  │ Planner  │  │  Memory  │  │  Tools   │  │
│  └──────────┘  └──────────┘  └──────────┘  │
│              ┌──────────────┐               │
│              │  行动执行器   │               │
│              │   Executor   │               │
│              └──────────────┘               │
└─────────────────────────────────────────────┘
```

- **规划器**：将复杂目标分解为可执行步骤（CoT、ToT、ReAct）
- **记忆库**：短期（上下文窗口）+ 长期（向量数据库/外部存储）
- **工具集**：API 调用、代码执行、文件操作、浏览器控制
- **执行器**：将规划输出转化为真实世界操作

### 1.2 主流框架对比

| 框架 | 定位 | 核心特性 | 适用场景 |
|------|------|----------|---------|
| **LangChain** | 通用编排 | Chain/Agent/Tool 抽象 | 快速原型，RAG 应用 |
| **AutoGen** | 多 Agent 对话 | 可配置对话流 | 代码生成、任务协作 |
| **CrewAI** | 角色分工 | 专业化 Agent 角色 | 团队协作模拟 |
| **LangGraph** | 有状态图 | 循环/条件/状态持久化 | 复杂工作流 |
| **OpenDevin** | 软件工程 | 代码+执行环境 | SWE 任务 |

---

## 二、规划与推理范式

### 2.1 ReAct：思考-行动-观察循环

ReAct（Reason + Act）是当前应用最广的 Agent 推理范式：

```
Thought: 我需要查询当前天气
Action: search("北京今天天气")
Observation: 晴，气温 22°C，微风
Thought: 已获得天气信息，可以回答用户
Answer: 今天北京天气晴朗，22°C，适合出行
```

**80/20 核心**：ReAct 循环 + 错误处理（重试 + 反思）覆盖了 80% 的实际 Agent 任务需求。

### 2.2 Tree of Thought (ToT)

适用于需要**探索多个解决路径**的任务：

```
目标: 解决数学问题
├── 路径 A: 代数方法 → 评估: 可行
│   ├── 子步骤 A1 → 评估: 好
│   └── 子步骤 A2 → 评估: 差，剪枝
└── 路径 B: 几何方法 → 评估: 更优
    └── 子步骤 B1 → 最终答案
```

**何时使用 ToT**：
- 问题有多个有效解法
- 需要回溯（某条路径失败后重来）
- 可以明确评估中间步骤质量

### 2.3 Reflexion：自我反思机制

```
尝试 1 → 失败 →
  反思: "我忽略了边界条件 X" →
尝试 2（融入反思）→ 成功
```

Reflexion 使 Agent 能从失败中学习，而无需重新训练模型。

---

## 三、工具使用与函数调用

### 3.1 工具调用标准模式

```json
// OpenAI/Anthropic 函数调用格式
{
  "name": "search_web",
  "description": "搜索互联网获取实时信息",
  "parameters": {
    "type": "object",
    "properties": {
      "query": {"type": "string", "description": "搜索查询"},
      "max_results": {"type": "integer", "default": 5}
    },
    "required": ["query"]
  }
}
```

### 3.2 工具选择策略

Agent 工具选择的 3 种主流方法：

1. **Few-shot 示例**：在提示中给出工具使用示例
2. **工具描述优化**：精心设计工具描述，使 LLM 能准确判断何时使用
3. **工具路由**：专门训练一个轻量分类器决定工具调用时机

**关键工程实践**：
- 工具数量 ≤ 20：超过此数量模型选择准确率显著下降
- 工具描述 < 200 tokens：过长描述消耗上下文且降低准确性
- 工具调用失败率监控：≥ 5% 需检查描述或参数设计

### 3.3 常用工具类型

| 类型 | 示例工具 | 主要用途 |
|------|---------|---------|
| 信息检索 | web_search, read_file | 获取上下文 |
| 代码执行 | python_repl, bash | 计算与操作 |
| 外部 API | weather, calendar | 真实世界操作 |
| 文件系统 | read, write, list | 持久化存储 |
| 浏览器 | click, type, screenshot | GUI 操作 |

---

## 四、记忆系统设计

### 4.1 记忆层次结构

```
┌─────────────────────────────────────┐
│     工作记忆 (Working Memory)        │
│     上下文窗口，对话历史              │
├─────────────────────────────────────┤
│     情节记忆 (Episodic Memory)       │
│     历史对话摘要，任务历史记录         │
├─────────────────────────────────────┤
│     语义记忆 (Semantic Memory)       │
│     知识库，向量数据库                │
├─────────────────────────────────────┤
│     程序记忆 (Procedural Memory)     │
│     技能、工具使用模式                │
└─────────────────────────────────────┘
```

### 4.2 MemGPT 式分层记忆

MemGPT 的核心思路：将"内存管理"本身作为一种工具调用，让 Agent 自行决定何时读写长期记忆。

```python
# Agent 自主管理记忆的示意
tools = [
    "core_memory_append",    # 追加到核心记忆
    "core_memory_replace",   # 替换核心记忆
    "archival_memory_insert", # 存入归档记忆
    "archival_memory_search", # 搜索归档记忆
    "recall_memory_search",  # 搜索回忆记忆
]
```

### 4.3 实践建议

- **短期任务**：仅用上下文窗口，无需外部记忆
- **长期交互**：使用滑动摘要 + 向量检索
- **知识密集**：预构建结构化知识库 + RAG
- **记忆遗忘**：定期清理低频访问记忆，避免噪声积累

---

## 五、多 Agent 系统

### 5.1 协作模式分类

**层级式 (Hierarchical)**：
```
   管理 Agent
   /    \
子 A   子 B
```
适用：任务可明确分解，有自然层级关系

**扁平式 (Flat/Peer)**：
```
A ←→ B ←→ C
```
适用：对等协作，角色互补

**市场式 (Market-based)**：
```
任务发布 → 竞价 → 分配执行
```
适用：动态任务分配，资源有限场景

### 5.2 多 Agent 设计原则

1. **角色分工明确**：每个 Agent 有专属能力和职责边界
2. **通信协议统一**：使用结构化消息格式（JSON/XML）
3. **冲突解决机制**：当 Agent 意见相左时有明确的仲裁规则
4. **故障隔离**：单个 Agent 失败不影响整体系统

### 5.3 代表性系统

| 系统 | Agent 数量 | 任务类型 | 核心创新 |
|------|-----------|---------|---------|
| **MetaGPT** | 5-8 | 软件开发 | 标准化工作流 (SOP) |
| **ChatDev** | 3-6 | 代码生成 | 对话驱动开发 |
| **AutoGen** | 2-N | 通用 | 灵活对话图 |
| **AgentVerse** | N | 模拟 | 动态 Agent 生命周期 |

---

## 六、Agent 评测基准

### 6.1 核心基准一览

| 基准 | 关注点 | 评测方式 | 难度 |
|------|--------|---------|------|
| **SWE-bench** | 代码修复 | GitHub issue → PR | 高 |
| **WebArena** | Web 导航 | 端到端任务完成 | 高 |
| **AgentBench** | 综合能力 | 8 类环境 | 中高 |
| **GAIA** | 问题求解 | 多步推理 | 中高 |
| **HumanEval** | 代码生成 | 单元测试 | 中 |
| **Mind2Web** | Web 理解 | 动作预测 | 中 |

### 6.2 SWE-bench 核心指标

SWE-bench 是当前代码 Agent 领域最重要的基准：
- 测试集：2,294 个真实 GitHub issue（12 个流行仓库）
- 评测：Agent 生成的代码补丁是否通过官方测试套件
- 2024 年 SOTA：~50% 解决率（从 2023 年的 1.7% 飞速提升）

---

## 七、Agent 安全

### 7.1 主要威胁模型

| 威胁类型 | 描述 | 缓解方案 |
|---------|------|---------|
| **提示注入** | 恶意内容操纵 Agent 行为 | 输入过滤、工具调用审计 |
| **目标泛化失败** | Agent 寻找意外的"捷径" | 奖励设计、规格约束 |
| **工具滥用** | 超权限工具调用 | 最小权限原则、审计日志 |
| **信息泄露** | Agent 泄露敏感上下文 | 输出过滤、数据分级 |
| **无限循环** | Agent 陷入循环不终止 | 步数限制、超时机制 |

### 7.2 生产安全实践

```python
# 安全沙箱示例
class SafeAgent:
    MAX_STEPS = 50           # 最大执行步数
    ALLOWED_TOOLS = [...]    # 工具白名单
    TIMEOUT_SECONDS = 300    # 总超时
    HUMAN_CONFIRM_ACTIONS = ["delete", "send_email", "payment"]  # 需人工确认的操作

    def execute(self, task):
        for step in range(self.MAX_STEPS):
            action = self.plan_next_action()
            if action.name in self.HUMAN_CONFIRM_ACTIONS:
                confirmed = self.request_human_approval(action)
                if not confirmed:
                    return "action_cancelled"
            result = self.run_with_timeout(action)
```

---

## 八、代码 Agent 工程

### 8.1 SWE-Agent 工作流

```
1. 读取 Issue 描述
2. 探索代码仓库结构
3. 定位相关文件
4. 理解上下文（相关函数、测试）
5. 生成补丁
6. 本地验证（运行测试）
7. 提交 PR
```

### 8.2 代码 Agent 核心工具集

```
file_viewer      - 查看文件内容（带行号）
code_editor      - 定向修改代码（指定行范围）
bash             - 运行命令（测试、构建）
search_in_file   - 文件内搜索
find_file        - 文件名搜索
```

### 8.3 工程经验

- **上下文窗口管理**：代码文件通常很长，需精确定位而非全量加载
- **增量修改优先**：小范围精确修改比重写整个文件更可靠
- **测试驱动验证**：每次修改后立即运行相关测试
- **错误信息利用**：详细的编译/运行错误是最好的反馈信号

---

## 九、Web 与 GUI Agent

### 9.1 Web Agent 技术栈

```
感知层: DOM 解析 / 截图 / 无障碍树 (Accessibility Tree)
理解层: 元素识别 / 意图推理 / 状态跟踪
行动层: click / type / scroll / navigate
```

### 9.2 主要挑战

| 挑战 | 描述 | 当前方案 |
|------|------|---------|
| **动态网页** | JS 渲染内容难以静态解析 | Playwright/Puppeteer 实时渲染 |
| **视觉定位** | 元素位置识别 | 截图 + 坐标预测 |
| **登录状态** | 多页面状态保持 | Cookie 管理 |
| **验证码** | 反机器人保护 | 人工干预点 |
| **长任务** | 多步骤状态丢失 | 检查点 + 状态序列化 |

### 9.3 Computer Use 新范式

Claude Computer Use（2024）引领了新一代 GUI Agent 范式：
- 直接操作像素级截图，不依赖 DOM 结构
- 统一了 Web/桌面/移动端操作接口
- 挑战：延迟高（截图→推理→执行），成本贵

---

## 十、生产部署关键指标

### 10.1 Agent 可靠性指标

| 指标 | 定义 | 目标 |
|------|------|------|
| 任务完成率 (TCR) | 成功完成任务的比例 | ≥ 80% |
| 平均步数 (Avg Steps) | 完成任务所需平均步骤数 | 越少越好 |
| 工具调用错误率 | 无效/失败工具调用比例 | < 5% |
| 平均延迟 | 端到端任务完成时间 | 业务决定 |
| 人工干预率 | 需要人工介入的比例 | < 10% |

### 10.2 可观测性最佳实践

```python
# Agent 运行时记录关键信息
trace = {
    "task_id": "uuid",
    "start_time": "ISO8601",
    "steps": [
        {
            "step": 1,
            "thought": "...",
            "action": {"name": "search", "args": {...}},
            "observation": "...",
            "duration_ms": 230,
        }
    ],
    "final_status": "success|failure|timeout",
    "total_tokens": 12500,
    "total_cost_usd": 0.045,
}
```

### 10.3 成本控制

- **模型分级**：简单子任务用小模型（GPT-4o-mini/Haiku），复杂推理用大模型
- **缓存策略**：相同子任务结果缓存复用
- **早停机制**：确定失败时提前终止，避免无谓消耗
- **Token 预算**：为每步推理设置最大 token 限制

---

## 参考资源

- [ReAct Paper](https://arxiv.org/abs/2210.03629) — Yao et al., 2022
- [Tree of Thought](https://arxiv.org/abs/2305.10601) — Yao et al., 2023
- [Reflexion](https://arxiv.org/abs/2303.11366) — Shinn et al., 2023
- [MemGPT](https://arxiv.org/abs/2310.08560) — Packer et al., 2023
- [SWE-bench](https://arxiv.org/abs/2310.06770) — Jimenez et al., 2023
- [WebArena](https://arxiv.org/abs/2307.13854) — Zhou et al., 2023
- [MetaGPT](https://arxiv.org/abs/2308.00352) — Hong et al., 2023

---

[English README](README.md) | [中文 README](README.zh-CN.md) | [返回主目录](../README.md)
