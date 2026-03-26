# QA & Quality Engineering — Knowledge Document

> 基于 3,069 篇论文摘要（2020–2026）提炼的现代质量工程知识体系

---

## 一、质量工程（QE）全局视角

### 1.1 QE vs 传统 QA

| 维度 | 传统 QA | 质量工程 (QE) |
|------|--------|--------------|
| 时机 | 开发完成后测试 | 贯穿全开发周期 |
| 角色 | 找 Bug | 防止 Bug，提升质量体系 |
| 工具 | 手工测试为主 | 自动化、可观测性、质量度量 |
| 影响力 | 执行测试 | 影响架构与工程文化 |
| 指标 | Bug 数量 | MTTR、部署频率、变更失败率 |

### 1.2 质量工程四支柱

```
┌─────────────────────────────────────────────┐
│           质量工程 (Quality Engineering)      │
│                                              │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │ 测试策略 │  │ 自动化    │  │ 可观测性 │  │
│  │ Strategy │  │Automation│  │ Observ.  │  │
│  └──────────┘  └──────────┘  └──────────┘  │
│              ┌──────────────┐               │
│              │  质量文化     │               │
│              │Quality Culture│              │
│              └──────────────┘               │
└─────────────────────────────────────────────┘
```

---

## 二、测试策略与层次

### 2.1 测试金字塔

```
           /\
          /  \
         / E2E \     ← 少量，慢，贵，高置信度
        /--------\
       /  集成测试  \   ← 适量，中速，关键交互
      /------------\
     /   单元测试    \  ← 大量，快，便宜，细粒度
    /________________\
```

**80/20 最佳实践**：
- 单元测试：70% of tests，运行 < 5 分钟
- 集成测试：20% of tests，关注服务边界
- E2E 测试：10% of tests，覆盖关键用户旅程

### 2.2 测试类型全景

| 测试类型 | 目的 | 触发时机 |
|---------|------|---------|
| 单元测试 | 函数/类级别正确性 | 每次提交 |
| 集成测试 | 组件间交互 | PR/合并 |
| API 测试 | 接口契约 | PR/合并 |
| E2E 测试 | 用户旅程完整性 | 每次部署 |
| 性能测试 | 负载、压力、容量 | 版本发布前 |
| 安全测试 | 漏洞扫描、渗透 | 版本发布前 |
| 混沌测试 | 故障韧性 | 生产持续 |
| 契约测试 | 消费者-提供者接口 | CI |

### 2.3 测试四象限

```
        ↑ 面向业务
   Q2   │  Q1
 探索性  │ 验收测试
 可用性  │ 功能测试
─────────┼─────────
   Q4   │  Q3
 性能测试│ 单元测试
 安全测试│ 集成测试
 混沌测试│ 组件测试
        │
        ↓ 面向技术
  ← 评判产品    支持团队 →
```

---

## 三、自动化测试框架

### 3.1 主流测试框架选择

| 语言 | 单元 | 集成 | E2E | API |
|------|------|------|-----|-----|
| JavaScript | Jest/Vitest | Testing Library | Playwright/Cypress | Supertest |
| Python | pytest | pytest + httpx | Playwright/Selenium | requests |
| Java | JUnit5 | Spring Test | Selenium/TestNG | REST Assured |
| Go | testing | testify | Rod/chromedp | httptest |

### 3.2 测试代码质量原则

**FIRST 原则**：
- **Fast**：测试应该快速执行
- **Independent**：测试间无相互依赖
- **Repeatable**：任何环境可重复
- **Self-Validating**：自动判断通过/失败
- **Timely**：与生产代码同步编写

**测试命名规范**：
```
// Given-When-Then 格式
test("Given user has insufficient balance, When attempting transfer, Then should throw InsufficientFundsError")

// Should 格式
test("should return 401 when token is expired")
```

### 3.3 测试数据管理

| 策略 | 描述 | 适用场景 |
|------|------|---------|
| **内联数据** | 测试中直接定义 | 单元测试 |
| **工厂函数** | 可定制的数据生成器 | 集成测试 |
| **Fixtures** | 预定义的数据集 | E2E 测试 |
| **数据库快照** | 恢复到已知状态 | 复杂场景测试 |

---

## 四、API 与契约测试

### 4.1 消费者驱动契约测试 (CDC)

传统方式的问题：
```
服务 A 假设 API: { "userId": 123, "name": "Alice" }
服务 B 实际返回: { "user_id": 123, "username": "Alice" }  ← 字段名不同！
生产环境才发现问题 ❌
```

CDC 解决方案（以 Pact 为例）：
```
1. 消费者编写期望契约（Pact 文件）
2. 发布契约到 Pact Broker
3. 提供者验证契约（无需消费者配合）
4. CI 中双向验证
```

### 4.2 API 测试分层

```python
# 层 1: 单元级别 - Mock HTTP
with mock.patch('requests.get') as mock_get:
    mock_get.return_value.json.return_value = {"id": 1}
    result = get_user(1)

# 层 2: 契约级别 - Pact / OpenAPI 验证
pact.verify_provider()

# 层 3: 集成级别 - 真实 HTTP，测试数据库
response = client.get("/api/users/1")
assert response.status_code == 200

# 层 4: E2E 级别 - 完整用户旅程
page.goto("/users")
page.click("#user-1")
assert page.inner_text("#name") == "Alice"
```

---

## 五、性能测试工程

### 5.1 性能测试类型

| 类型 | 目标 | 工具 |
|------|------|------|
| **负载测试** | 正常/峰值负载下的行为 | k6, JMeter, Gatling |
| **压力测试** | 超出容量后的行为 | k6, Artillery |
| **峰值测试** | 突发流量响应 | k6 |
| **耐久测试** | 长时间稳定性 | k6, JMeter |
| **容量测试** | 系统最大容量 | 二分法探测 |

### 5.2 关键性能指标 (SLIs)

```
延迟 (Latency)
  ├── P50 (中位数): 正常体验
  ├── P95: 大多数用户的体验
  ├── P99: 长尾体验
  └── P99.9: SLA 相关
吞吐量 (Throughput): RPS/TPS
错误率 (Error Rate): 4xx/5xx 比例
饱和度 (Saturation): CPU/内存使用率
```

### 5.3 性能测试最佳实践

```javascript
// k6 基础负载测试
import http from 'k6/http';
import { check, sleep } from 'k6';

export const options = {
  stages: [
    { duration: '2m', target: 100 },  // 爬坡
    { duration: '5m', target: 100 },  // 稳定
    { duration: '2m', target: 0 },    // 降坡
  ],
  thresholds: {
    http_req_duration: ['p(95)<500'],  // 95% 请求 < 500ms
    http_req_failed: ['rate<0.01'],    // 错误率 < 1%
  },
};

export default function() {
  const res = http.get('https://api.example.com/users');
  check(res, { 'status was 200': (r) => r.status == 200 });
  sleep(1);
}
```

---

## 六、混沌工程

### 6.1 混沌工程原则

> "在受控条件下主动制造故障，以在实际故障前发现系统弱点。"

**Netflix 混沌猴 (Chaos Monkey) 影响**：
- 通过随机关闭生产实例测试系统韧性
- 推动整个行业采纳混沌工程实践

### 6.2 混沌实验设计

```
1. 定义稳态 (Steady State)
   例: 错误率 < 0.1%, P99 < 200ms

2. 提出假设 (Hypothesis)
   "如果我们关闭一个数据库副本，系统仍能正常服务"

3. 设计实验 (Experiment)
   注入: 关闭 DB 副本
   持续时间: 5 分钟
   影响范围: 5% 流量 (从小范围开始)

4. 执行并观察
   监控关键指标是否在稳态范围内

5. 学习与改进
   记录结果，修复发现的弱点
```

### 6.3 混沌工具

| 工具 | 适用层 | 特点 |
|------|--------|------|
| **Chaos Monkey** | 实例/服务 | Netflix 出品，Kubernetes 友好 |
| **LitmusChaos** | Kubernetes | 云原生，CNCF 项目 |
| **Gremlin** | 多层 | 商业，最完整的故障类型 |
| **Toxiproxy** | 网络 | 网络故障模拟（延迟、断连） |
| **Fault** | 代码级 | 轻量、嵌入式测试 |

---

## 七、AI/ML 系统测试

### 7.1 ML 测试的特殊挑战

| 挑战 | 传统软件 | ML 系统 |
|------|---------|---------|
| 确定性 | 相同输入→相同输出 | 概率性，输出可变 |
| 正确性 | 有明确规格 | 无精确"正确"答案 |
| 边界 | 可枚举 | 输入空间无限大 |
| 退化 | 代码回归 | 数据/模型漂移 |

### 7.2 ML 测试分层

```
数据测试
  ├── Schema 验证（类型、范围）
  ├── 分布测试（特征分布稳定性）
  └── 数据漂移检测 (PSI/KL 散度)

模型测试
  ├── 训练-服务一致性（特征对齐）
  ├── 性能指标回归（AUC/F1/RMSE）
  └── 偏见测试（群体公平性）

推理测试
  ├── 端到端功能测试
  ├── 延迟/吞吐量测试
  └── 不变性测试（语义等价输入）

行为测试 (Behavioral Testing)
  ├── 最小功能测试 (MFT)
  ├── 不变性测试 (INV)
  └── 方向期望测试 (DIR)
```

### 7.3 LLM 评测工程

LLM 评测的特殊挑战：开放性输出难以自动评分。

**评测方法**：
1. **LLM-as-Judge**：用强模型评估弱模型输出
2. **人工评测 (Human Eval)**：专家打分，成本高
3. **基准数据集**：MMLU、HumanEval、TruthfulQA 等
4. **A/B 对比**：用户偏好投票
5. **领域专属指标**：代码执行通过率、事实核查等

```python
# LLM-as-Judge 示例
def llm_judge(question, response, criteria):
    prompt = f"""
    问题: {question}
    回答: {response}

    评估该回答是否符合以下标准（1-5分）：
    - 准确性: {criteria['accuracy']}
    - 完整性: {criteria['completeness']}
    - 简洁性: {criteria['conciseness']}

    请给出每项分数和总体评价。
    """
    return judge_llm.generate(prompt)
```

---

## 八、可观测性与生产质量

### 8.1 可观测性三支柱

```
日志 (Logs)
  ← 结构化 JSON 日志
  ← 关联 ID (Correlation ID) 贯穿全链路
  ← 日志级别：ERROR > WARN > INFO > DEBUG

指标 (Metrics)
  ← RED: Rate, Errors, Duration
  ← USE: Utilization, Saturation, Errors
  ← 业务指标 (Business KPIs)

链路追踪 (Traces)
  ← 分布式跟踪 (OpenTelemetry)
  ← Span: 一个操作的时间记录
  ← Trace: 跨服务的操作链
```

### 8.2 SRE 可靠性指标

**SLO/SLI/SLA 体系**：

```
SLI (Service Level Indicator): 实际测量值
  例: 过去 30 天 P99 延迟

SLO (Service Level Objective): 内部目标
  例: P99 延迟 ≤ 500ms (99.9% 的 30 天窗口)

SLA (Service Level Agreement): 对外承诺
  例: 可用性 99.9% (违反则退款)

错误预算 (Error Budget) = 1 - SLO
  例: 99.9% SLO → 0.1% 错误预算 = ~8.7 小时/年
```

### 8.3 事故响应与复盘

**MTTR 分解**：
```
MTTR = MTTD + MTTI + MTTF + MTTV
  MTTD: Mean Time To Detect    (监控告警延迟)
  MTTI: Mean Time To Investigate (定位时间)
  MTTF: Mean Time To Fix       (修复时间)
  MTTV: Mean Time To Verify    (验证时间)
```

**无责复盘 (Blameless Post-Mortem)**：
1. 事故概述（时间线）
2. 根本原因分析（5 Why）
3. 贡献因素（人、流程、工具）
4. 改进措施（具体、可追踪）
5. 经验教训（系统性改进）

---

## 九、质量度量体系

### 9.1 DORA 四项关键指标

| 指标 | 描述 | 精英表现 |
|------|------|---------|
| **部署频率** | 多久部署一次 | 按需（多次/天） |
| **变更前置时间** | 提交到生产的时间 | < 1 小时 |
| **服务恢复时间 (MTTR)** | 故障到恢复的时间 | < 1 小时 |
| **变更失败率** | 导致故障的部署比例 | 0–15% |

### 9.2 测试有效性指标

| 指标 | 计算方式 | 健康值 |
|------|---------|--------|
| 代码覆盖率 | 被测代码 / 总代码 | > 80% |
| 突变测试得分 | 被杀死突变体 / 总突变体 | > 70% |
| 缺陷泄漏率 | 生产缺陷 / 总缺陷 | < 5% |
| 测试执行时间 | CI 总时长 | < 15 分钟 |
| 测试稳定性 | 1 - 偶发失败率 | > 99% |

### 9.3 质量看板 (Quality Dashboard)

一个高效质量看板应包含：
- **生产**：错误率、P99 延迟、可用性
- **测试**：通过率、覆盖率、执行时间、偶发失败
- **流程**：DORA 四指标、技术债趋势
- **安全**：开放漏洞数量、最老未修复漏洞年龄

---

## 十、探索性测试与测试策略

### 10.1 探索性测试技术

**基于会话的探索性测试 (SBET)**：
```
会话宪章: 测试区域 + 目标 + 时间限制
  例: "在用户注册流程中探索边界条件 [60分钟]"

执行:
  - 基于直觉和经验快速探索
  - 记录测试思路、发现、问题
  - 使用工具辅助（代理拦截、日志监控）

产出:
  - 测试笔记（可重现的 Bug）
  - 覆盖报告（探索了哪些区域）
  - 改进建议（风险区域）
```

### 10.2 基于风险的测试优先级

```
风险矩阵:
                        高概率
                          ↑
高影响 ─ 优先测试 │ 立即修复 ─→ 高概率
                  │
                  │
低影响 ─ 最低优先 │ 监控即可
                          ↓
                        低概率
```

**优先级公式**：测试优先级 = 业务影响 × 失败概率 × 变更频率

---

## 参考资源

- [DORA State of DevOps](https://dora.dev/) — 年度行业报告
- [Google SRE Book](https://sre.google/sre-book/table-of-contents/) — Google
- [Testing Trophy](https://kentcdodds.com/blog/the-testing-trophy-and-testing-classifications) — Kent C. Dodds
- [Pact Contract Testing](https://pact.io/) — 消费者驱动契约
- [Chaos Engineering](https://principlesofchaos.org/) — Netflix
- [LitmusChaos](https://litmuschaos.io/) — CNCF 混沌工程
- [Accelerate](https://itrevolution.com/accelerate-book/) — DORA 研究基础

---

[English README](README.md) | [中文 README](README.zh-CN.md) | [返回主目录](../README.md)
