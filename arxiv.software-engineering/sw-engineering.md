# Software Engineering — Knowledge Document

> 基于 4,418 篇论文摘要（2020–2026）提炼的现代软件工程知识体系

---

## 一、桌面与前端开发

### 1.1 跨平台桌面框架对比

| 框架 | 技术栈 | 包体大小 | 性能 | 适用场景 |
|------|--------|---------|------|---------|
| **Electron** | Chromium + Node.js | 大 (~100MB) | 中 | 功能优先，VS Code/Slack |
| **Tauri** | WebView + Rust | 小 (~3MB) | 高 | 轻量工具类应用 |
| **Flutter Desktop** | Dart | 中 | 高 | 移动优先的桌面扩展 |
| **Qt** | C++ | 中 | 极高 | 专业工具软件 |
| **MAUI** | .NET | 中 | 高 | Microsoft 生态 |

### 1.2 现代前端架构趋势

**2020–2026 主流演进**：
```
jQuery → React/Vue/Angular → 岛屿架构 (Islands Architecture)
                           → 服务端组件 (RSC)
                           → 信号 (Signals) 反应式系统
```

**80/20 核心**：
- React + TypeScript + Tailwind 覆盖 ~70% 的现代前端需求
- Next.js 等元框架统一了 CSR/SSR/SSG 的选择

---

## 二、UI/UX 设计工程

### 2.1 设计系统工程化

优秀设计系统的三要素：
1. **组件库**：可复用的 UI 原子（Button、Input、Card...）
2. **设计 Token**：颜色、字体、间距的单一真相来源
3. **文档 + Storybook**：活文档，组件可交互展示

```css
/* 设计 Token 示例 */
:root {
  --color-primary-500: #3B82F6;
  --spacing-4: 1rem;
  --font-body: 'Inter', sans-serif;
  --radius-md: 0.375rem;
}
```

### 2.2 可访问性 (Accessibility) 工程

**WCAG 2.1 AA 级**是工程最低标准：
- 色彩对比度 ≥ 4.5:1（正文）
- 所有交互元素可键盘操作
- 屏幕阅读器支持（ARIA 语义）
- 无纯色觉依赖的信息传达

**自动化工具**：axe-core, Lighthouse, WAVE

---

## 三、软件架构

### 3.1 架构演化路径

```
单体架构 (Monolith)
    ↓ 规模增长
模块化单体 (Modular Monolith)  ← 常被忽视的最佳中间态
    ↓ 独立部署需求
微服务 (Microservices)
    ↓ 通信复杂度高时
事件驱动架构 (EDA) / 服务网格
```

**80/20 实践**：大多数系统应止步于"模块化单体"，微服务的分布式复杂性收益通常被高估。

### 3.2 六边形架构 / 端口与适配器

```
┌─────────────────────────────────────┐
│           应用核心 (Domain)          │
│  ┌────────────────────────────────┐ │
│  │    端口 (Ports / Interfaces)   │ │
│  └────────┬──────────────┬────────┘ │
└───────────┼──────────────┼──────────┘
            ↑              ↑
     适配器 (Adapters)  适配器 (Adapters)
   HTTP API / CLI      DB / MQ / 外部服务
```

**核心价值**：业务逻辑与技术细节解耦，基础设施可随时替换。

### 3.3 现代分布式系统模式

| 模式 | 解决问题 | 典型实现 |
|------|---------|---------|
| **CQRS** | 读写路径分离 | 命令总线 + 投影 |
| **Event Sourcing** | 审计、时间旅行 | Kafka + 事件日志 |
| **Saga** | 分布式事务 | 编排式 or 协同式 |
| **Circuit Breaker** | 级联故障隔离 | Hystrix/Resilience4j |
| **Outbox Pattern** | 消息可靠投递 | DB + MQ 原子性 |

---

## 四、代码质量

### 4.1 代码质量四维度

```
可读性 (Readability)
  ├── 命名清晰、意图明确
  ├── 函数单一职责
  └── 适度注释（解释"为什么"而非"是什么"）

可维护性 (Maintainability)
  ├── 低耦合、高内聚
  ├── 依赖注入、接口抽象
  └── 圈复杂度 < 10

可测试性 (Testability)
  ├── 纯函数优先
  ├── 依赖可注入
  └── 副作用隔离

性能 (Performance)
  ├── 算法复杂度适当
  ├── 避免 N+1 查询
  └── 关键路径无不必要分配
```

### 4.2 技术债管理

**技术债四象限**：
```
             故意的          无意的
鲁莽的  "没时间做对的"   "不知道有更好的方式"
谨慎的  "必须快速上线，   "现在知道该怎么做了"
        之后再重构"
```

**80/20 实践**：
- 每个 Sprint 分配 15–20% 时间处理技术债
- 用"童子军规则"：每次离开代码时比来时更干净
- 高频变更的代码优先偿还技术债

---

## 五、安全工程

### 5.1 OWASP Top 10（2021）

| 排名 | 漏洞类型 | 防御方案 |
|------|---------|---------|
| A01 | 访问控制失效 | RBAC + 默认拒绝 |
| A02 | 加密失败 | 强加密算法 + 密钥管理 |
| A03 | 注入 | 参数化查询 + 输入验证 |
| A04 | 不安全设计 | 威胁建模 + 安全设计模式 |
| A05 | 安全配置错误 | IaC + 配置扫描 |
| A06 | 过时的组件 | SCA + 自动更新 |
| A07 | 认证失败 | MFA + 会话管理 |
| A08 | 完整性失败 | 数字签名 + CI/CD 安全 |
| A09 | 日志监控不足 | SIEM + 告警 |
| A10 | 服务器端请求伪造 | 网络分段 + 出口过滤 |

### 5.2 DevSecOps 集成

```yaml
# CI/CD 安全门控示例
stages:
  - sast:          # 静态分析 (Sonar/Semgrep)
  - sca:           # 依赖扫描 (Snyk/OWASP DC)
  - secrets_scan:  # 密钥扫描 (Gitleaks/TruffleHog)
  - dast:          # 动态分析 (OWASP ZAP)
  - container_scan: # 容器扫描 (Trivy/Grype)
```

---

## 六、DevOps 与 CI/CD

### 6.1 现代 CI/CD 流水线

```
代码提交
  → 触发 CI
    → 单元测试 (< 5min)
    → 静态分析 + Lint
    → 构建 + 容器化
    → 集成测试 (< 15min)
    → 安全扫描
  → 部署到 Staging
    → E2E 测试
    → 性能基准测试
  → 人工审批 (可选)
  → 部署到 Production
    → 金丝雀发布 (Canary)
    → 指标监控 + 自动回滚
```

### 6.2 Platform Engineering

2022 年后兴起的"内部开发者平台 (IDP)"趋势：

| 传统 DevOps | Platform Engineering |
|------------|---------------------|
| 每个团队自己搭基础设施 | 平台团队提供黄金路径 |
| 开发者学习大量 K8s/AWS | 开发者用自服务门户 |
| 高认知负担 | 低认知负担 |

**核心工具**：Backstage (开发者门户), Crossplane (基础设施抽象), ArgoCD (GitOps)

### 6.3 GitOps 核心原则

1. **声明式**：系统状态用 Git 中的文件描述
2. **版本化**：所有变更有历史可追溯
3. **自动化**：GitOps 算子自动协调实际状态与期望状态
4. **持续对账**：持续检查并修复漂移

---

## 七、AI 辅助开发

### 7.1 AI 编程工具分类

| 工具类型 | 代表产品 | 使用场景 |
|---------|---------|---------|
| 代码补全 | GitHub Copilot, Cursor | 行/函数级补全 |
| 代码对话 | Claude, GPT-4, Gemini | 解释、重构、调试 |
| 代码 Agent | Devin, SWE-agent, Aider | 自主完成任务 |
| 代码审查 | CodeRabbit, Greptile | PR 审查 |
| 文档生成 | Mintlify, Swimm | 自动文档 |

### 7.2 AI 辅助开发 80/20 实践

**高价值使用场景**：
- 样板代码生成（CRUD、测试骨架）
- 代码解释（快速理解遗留代码）
- 调试辅助（错误信息分析）
- 重构建议
- 单元测试生成

**低价值 / 需谨慎**：
- 核心业务逻辑的完全生成（需严格验证）
- 安全敏感代码（需人工审查）
- 架构决策（AI 擅长战术，不擅长战略）

### 7.3 Copilot 效果研究

GitHub 2023 研究数据：
- 生产力提升：~55%（自感评估）
- 代码被采纳率：~30%（Copilot 建议中被接受的比例）
- 测试覆盖率：使用者反而写更少测试的趋势（需警惕）

---

## 八、软件哲学与工程品味

### 8.1 Unix 哲学

> "做一件事，并把它做好。"

核心原则：
1. 单一职责：每个程序做好一件事
2. 通用接口：文本流是万能通信媒介
3. 可组合性：小工具通过管道组合
4. 透明性：输出可被其他程序消费

**现代适用性**：微服务、函数即服务 (FaaS)、Unix 工具思维仍是设计好 API 和工具的基础。

### 8.2 可读性 vs 聪明性

> "代码是写给人看的，顺便让机器执行。" — Hal Abelson（大意）

```python
# 聪明的代码（避免）
result = [x for x in data if (lambda y: y > 0)(x)]

# 可读的代码（推荐）
def is_positive(value):
    return value > 0

result = [x for x in data if is_positive(x)]
```

**80/20 原则**：代码被读的次数远多于被写的次数，每次节省 5 秒写作时间可能浪费 5 分钟阅读时间。

### 8.3 渐进式设计

> "让它能用 → 让它正确 → 让它快"

- **先能用**：快速验证方向，避免过早优化
- **再正确**：加测试、处理边界、确保可靠性
- **后优化**：在有性能数据的前提下精准优化

**过早优化是万恶之源**（Knuth），但**从不优化也是工程失职**——差别在于基于数据还是猜测。

---

## 九、数据库设计原则

### 9.1 数据建模选择

| 场景 | 推荐方案 | 原因 |
|------|---------|------|
| 结构化业务数据 | PostgreSQL (关系型) | ACID、丰富查询 |
| 高写吞吐、简单查询 | MongoDB / DynamoDB | 水平扩展 |
| 全文搜索 | Elasticsearch | 倒排索引 |
| 时序数据 | TimescaleDB / InfluxDB | 时间优化存储 |
| 图关系 | Neo4j | 多跳关系查询 |
| 缓存 | Redis | 内存速度 |

### 9.2 数据库反模式

| 反模式 | 描述 | 解决方案 |
|--------|------|---------|
| N+1 查询 | 循环中逐条查询 | JOIN / 预加载 / DataLoader |
| 过度规范化 | 读取需大量 JOIN | 适度反规范化 + 视图 |
| 无索引的大表 | 全表扫描 | 覆盖索引 + 查询分析 |
| 宽表 | 一张表 500 列 | 垂直分割 |
| 神 ID | UUID 作为主键但无序 | ULIDv7 / 有序 UUID |

---

## 十、需求分解与项目管理

### 10.1 用户故事拆分技术

**INVEST 原则**：独立 (Independent)、可协商 (Negotiable)、有价值 (Valuable)、可估算 (Estimable)、适当小 (Small)、可测试 (Testable)

**故事拆分模式**：
1. **按工作流步骤**：注册 → 填信息 → 验证 → 确认
2. **按数据变化**：新建 vs 编辑 vs 删除
3. **按角色**：管理员视图 vs 用户视图
4. **按规则**：Happy Path 先行，边界条件后行
5. **按性能**：功能先实现，优化作为独立故事

### 10.2 技术任务估算

**斐波那契点数 + 三点估算**：
```
最乐观 (O) = 1 天
最悲观 (P) = 5 天
最可能 (M) = 2 天

期望估算 = (O + 4M + P) / 6 = (1 + 8 + 5) / 6 ≈ 2.3 天
```

**经验法则**：
- 任何估算 > 3 天的任务，先拆分再估算
- 预留 20% 缓冲用于不可见复杂度
- 历史速度 (Velocity) 是最准确的估算基础

---

## 参考资源

- [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) — Robert C. Martin
- [The Twelve-Factor App](https://12factor.net/) — Herwig, et al.
- [DORA State of DevOps](https://dora.dev/) — 年度行业报告
- [GitOps Principles](https://opengitops.dev/) — OpenGitOps
- [OWASP Top 10](https://owasp.org/Top10/) — OWASP Foundation
- [Accelerate](https://itrevolution.com/accelerate-book/) — Nicole Forsgren 等

---

[English README](README.md) | [中文 README](README.zh-CN.md) | [返回主目录](../README.md)
