[**English README**](README.md)

# arxiv.software-engineering — 软件工程研究摘要库（2020–2026）

> **来源：** 4,418 篇唯一 arXiv 摘要，来自 42 组关键词搜索（原始结果 6,822 篇，去重后保留），cs 类目，2020–2026，按相关性排序。
> **覆盖范围：** 前端与用户体验、软件架构、代码质量、需求工程、DevOps、安全工程、性能工程、AI 辅助开发、软件设计哲学。

---

## 摘要年份分布

| 年份 | 论文数 | 目录 |
|------|--------|------|
| 2020 | 402 | [2020/abstracts/](2020/abstracts/) |
| 2021 | 509 | [2021/abstracts/](2021/abstracts/) |
| 2022 | 457 | [2022/abstracts/](2022/abstracts/) |
| 2023 | 673 | [2023/abstracts/](2023/abstracts/) |
| 2024 | 948 | [2024/abstracts/](2024/abstracts/) |
| 2025 | 1,160 | [2025/abstracts/](2025/abstracts/) |
| 2026 | 269 | [2026/abstracts/](2026/abstracts/) |
| **合计** | **4,418** | |

> 6,822 条原始结果 → 去重后保留 4,418 篇。2024–2026 年共 2,377 篇（占语料库 54%），反映出近年论文发表量的加速增长。

---

## 搜索主题（42 组搜索）

| # | 主题 | 关键词 | 论文数 | 结果文件 | 被推翻的理论 / 既定谬误 |
|---|------|--------|--------|------------|
| 01 | 前端工程与 Web 开发 | frontend or front-end or web UI | 149 | [01-frontend.json](search-results/01-frontend.json) | "Frontend is just HTML/CSS, not real engineering" → Frontend has become a full engineering discipline with complex state management, performance optimization, and accessibility requirements. |
| 02 | UI 设计系统与组件库 | user interface design or UI design | 113 | [02-ui-design.json](search-results/02-ui-design.json) | "REST APIs are always the right choice" → GraphQL, gRPC, and event-driven architectures each dominate specific use cases; REST is not universally optimal. |
| 03 | 用户体验（UX）研究与评估 | user experience or UX design | 94 | [03-ux-design.json](search-results/03-ux-design.json) | "Microservices always improve scalability" → Premature microservice decomposition introduces distributed systems complexity (network failures, eventual consistency) that monoliths avoid. |
| 04 | 可用性测试与启发式评估 | usability testing or usability evaluation | 157 | [04-usability.json](search-results/04-usability.json) | "SQL databases don't scale" → Google Spanner, CockroachDB, and PlanetScale demonstrate that relational databases scale globally with proper distributed design. |
| 05 | 人机交互（HCI） | human computer interaction | 146 | [05-hci.json](search-results/05-hci.json) | "NoSQL databases are schema-free and always flexible" → Schema-on-read creates data quality problems; schema governance is required regardless of database type. |
| 06 | 无障碍与包容性设计 | accessibility software or application | 87 | [06-accessibility.json](search-results/06-accessibility.json) | "Caching is a simple performance fix" → Cache invalidation is one of the hardest problems in CS; incorrect caching causes harder-to-debug data consistency bugs than the original performance issue. |
| 07 | 桌面与原生应用开发 | desktop application or desktop app | 76 | [07-desktop-app.json](search-results/07-desktop-app.json) | "Synchronous request-response is always simpler" → In distributed systems, synchronous coupling creates cascading failures; async messaging provides better resilience. |
| 08 | 移动应用开发 | mobile app or mobile application | 200 | [08-mobile-app.json](search-results/08-mobile-app.json) | "Cloud is always cheaper than on-premise" → Cloud costs scale with usage; workloads with predictable high utilization often have lower TCO on owned hardware. |
| 09 | 软件架构与设计模式 | software architecture | 200 | [09-sw-architecture.json](search-results/09-sw-architecture.json) | "Containers solve the 'works on my machine' problem completely" → Containers solve OS-level dependencies but not secrets management, networking, or data persistence differences between environments. |
| 10 | 微服务与面向服务架构 | microservices or service mesh | 191 | [10-microservices.json](search-results/10-microservices.json) | "Kubernetes is required for all containerized workloads" → Kubernetes adds significant operational overhead; simpler orchestrators (ECS, Fly.io, Railway) are more appropriate for most applications. |
| 11 | 分布式系统与云原生工程 | cloud native or cloud computing software | 200 | [11-cloud-native.json](search-results/11-cloud-native.json) | "CI/CD pipelines guarantee software quality" → CI/CD automates delivery; quality requires test coverage, code review, and observability — pipelines are only the delivery mechanism. |
| 12 | API 设计与集成模式 | API design or REST API or GraphQL | 138 | [12-api-design.json](search-results/12-api-design.json) | "Infrastructure as Code eliminates configuration drift" → IaC eliminates untracked manual changes but doesn't prevent incorrect configurations that drift from intent over time. |
| 13 | 数据库设计与数据访问模式 | database design or data access | 200 | [13-distributed-sys.json](search-results/13-distributed-sys.json) | "DevOps is just developers doing operations" → DevOps is a cultural and organizational practice of shared ownership and feedback loops, not just a role reassignment. |
| 14 | 代码质量与静态分析 | code quality or software quality | 200 | [15-code-quality.json](search-results/15-code-quality.json) | "Security scanning tools make code secure" → SAST/DAST find known vulnerability patterns; security requires threat modeling, design review, and a security culture. |
| 15 | 技术债与代码坏味道 | technical debt | 200 | [14-technical-debt.json](search-results/14-technical-debt.json) | "OAuth 2.0 and OIDC are interchangeable" → OAuth 2.0 handles authorization (access); OIDC adds authentication (identity) on top — they solve different problems. |
| 16 | 重构与软件演进 | refactoring software | 200 | [16-refactoring.json](search-results/16-refactoring.json) | "HTTPS encrypts everything" → HTTPS encrypts transport only; data at rest, internal service traffic, and application-level vulnerabilities remain unprotected. |
| 17 | 程序理解与代码阅读 | program comprehension or code comprehension | 200 | [19-prog-comprehension.json](search-results/19-prog-comprehension.json) | "AI/LLM code generation is production-ready without review" → LLMs hallucinate APIs, produce subtly insecure code, and miss domain-specific invariants; human review remains essential. |
| 18 | 代码评审与协作开发 | code review | 200 | [17-code-review.json](search-results/17-code-review.json) | "Large language models understand code" → LLMs pattern-match on code syntax and semantics; they lack grounded understanding of runtime behavior, system constraints, and intent. |
| 19 | 需求工程与需求获取 | requirements engineering or elicitation | 200 | [20-requirements.json](search-results/20-requirements.json) | "Python is too slow for production" → With async I/O, NumPy/PyTorch, and compiled extensions, Python powers ML, data pipelines, and web services at scale. |
| 20 | 敏捷、Scrum 与精益开发 | agile or scrum software development | 200 | [22-agile-scrum.json](search-results/22-agile-scrum.json) | "Rust is too complex for most projects" → Rust's ownership model eliminates memory safety bugs; its complexity is justified for systems requiring performance + safety. |
| 21 | CI/CD 与发布工程 | CI/CD or continuous integration or delivery | 200 | [23-cicd.json](search-results/23-cicd.json) | "Object-oriented programming is the best paradigm" → Functional programming (immutability, pure functions) demonstrably reduces concurrency bugs; the paradigm war is settled in favor of multi-paradigm. |
| 22 | DevOps 与平台工程 | DevOps | 200 | [24-devops.json](search-results/24-devops.json) | "Design patterns are universally applicable" → GoF patterns were designed for OOP in statically typed languages; many are anti-patterns in functional or dynamic languages. |
| 23 | 软件文档与知识管理 | software documentation or API documentation | 63 | [25-documentation.json](search-results/25-documentation.json) | "Technical debt is always bad and should be minimized" → Deliberate technical debt that accelerates learning is a rational investment; the problem is debt that goes untracked and unrepaid. |
| 24 | 开发者生产力与体验 | developer productivity or developer experience | 76 | [26-dev-productivity.json](search-results/26-dev-productivity.json) | "Code complexity metrics predict maintenance difficulty" → Cyclomatic complexity correlates weakly with bug rates; test coverage and coupling are better predictors. |
| 25 | AI 辅助软件开发 | large language model software engineering | 200 | [39-llm-sw-eng.json](search-results/39-llm-sw-eng.json) | "Automated code review catches all code quality issues" → Static analysis misses semantic correctness, architectural violations, and performance regressions; human review remains essential. |
| 26 | 开源与社区开发 | open source software development | 200 | [28-open-source.json](search-results/28-open-source.json) | "Agile means no documentation" → Agile prioritizes working software over comprehensive documentation; it does not eliminate the need for architecture decisions, API contracts, and runbooks. |
| 27 | 应用安全工程 | application security or secure software | 200 | [30-app-security.json](search-results/30-app-security.json) | "Scrum is the definitive agile framework" → Scrum is one implementation of agile; Kanban, Shape Up, and custom adaptations often outperform Scrum in specific contexts. |
| 28 | 漏洞检测与分析 | vulnerability detection or vulnerability analysis | 200 | [31-vuln-detection.json](search-results/31-vuln-detection.json) | "Story points measure productivity" → Story points measure relative complexity for planning; using them to compare teams or measure output destroys their value. |
| 29 | 隐私工程与合规 | privacy engineering or data privacy software | 136 | [33-privacy-eng.json](search-results/33-privacy-eng.json) | "Code review is a bottleneck" → Code review is a knowledge transfer and quality mechanism; removing it increases defect rates and knowledge silos. |
| 30 | 认证、授权与身份管理 | authentication or authorization software | 200 | [34-auth-systems.json](search-results/34-auth-systems.json) | "Pair programming is always inefficient" → Research shows pair programming reduces defect rates by 15–50% while increasing implementation time by only 15%; it's often net positive. |
| 31 | 软件供应链安全 | software supply chain security | 42 | [35-supply-chain-sec.json](search-results/35-supply-chain-sec.json) | "Feature flags are only for A/B testing" → Feature flags enable dark launches, progressive rollouts, operational kill switches, and canary releases — they're a core deployment risk management tool. |
| 32 | 性能工程与性能分析 | software performance or performance optimization | 200 | [36-sw-performance.json](search-results/36-sw-performance.json) | "Monitoring and observability are the same" → Monitoring measures known failure modes (dashboards, alerts); observability answers unknown questions about system state from telemetry. |
| 33 | 可观测性、监控与日志 | observability or distributed tracing software | 144 | [37-observability.json](search-results/37-observability.json) | "Database migrations are always risky" → With expand-contract pattern and backward-compatible migrations, schema changes can be deployed without downtime or risk. |
| 34 | LLM 与软件工程 | AI code generation or LLM | 200 | [40-ai-code-gen.json](search-results/40-ai-code-gen.json) | "ORM frameworks cause performance problems" → ORMs cause N+1 query problems only when used without understanding; properly used ORMs generate efficient queries. |
| 35 | 软件哲学与设计品味 | software design philosophy or simplicity | 20 | [42-sw-philosophy.json](search-results/42-sw-philosophy.json) | "AI will make software engineers obsolete" → AI changes the distribution of tasks (less boilerplate, more design/architecture), but software engineering judgment, architecture, and debugging require human expertise. |
| 36 | 设计模式（补充） | design pattern software | 200 | [09-design-pattern.json](search-results/09-design-pattern.json) | "Documentation is write-once" → Living documentation (ADRs, runbooks, API specs as code) must be maintained alongside code; stale docs are worse than no docs. |
| 37 | 分布式系统（补充） | distributed systems software | 200 | [12-distributed-sys.json](search-results/12-distributed-sys.json) | "The CAP theorem means distributed systems must choose consistency or availability" → CAP applies only during network partitions; PACELC extends it to normal operation latency-consistency trade-offs. |
| 38 | 软件规格说明（补充） | software specification or formal specification | 200 | [21-sw-specification.json](search-results/21-sw-specification.json) | "Event sourcing solves all state management problems" → Event sourcing adds complexity (event schema evolution, replay performance, eventual consistency); it's appropriate for specific domains, not all systems. |
| 39 | 结对编程与协作（补充） | pair programming or collaborative coding | 29 | [29-pair-programming.json](search-results/29-pair-programming.json) | "Serverless eliminates operational concerns" → Serverless shifts infrastructure management to cold starts, vendor lock-in, observability gaps, and concurrency limits. |
| 40 | 静态分析安全（补充） | static analysis security | 200 | [32-static-analysis.json](search-results/32-static-analysis.json) | "GraphQL is always better than REST" → GraphQL adds client complexity and caching difficulty; REST with proper resource design is simpler and often more performant for non-complex use cases. |
| 41 | AI 软件开发（补充） | AI software development or software engineer | 200 | [41-ai-sw-dev.json](search-results/41-ai-sw-dev.json) | "Code formatting style doesn't matter" → Consistent automated formatting (Prettier, Black, gofmt) measurably reduces cognitive load in code review and merge conflicts. |
| 42 | 性能分析（补充） | profiling or performance profiling software | 200 | [38-profiling.json](search-results/38-profiling.json) | "Senior engineers write more code than junior engineers" → Senior engineers write less code and more architecture, design docs, and reviews; code output is inversely correlated with seniority. |

---

## 类目全景与二八定律分析

### 集群 A：前端、UI 与用户体验

**A01 前端工程与 Web 开发**（304 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **基于组件的架构**：React/Vue/Angular 组件模型 + 单向数据流 | 覆盖 80% 的现代 Web UI 可维护性和可测试性收益 — 论文一致表明与 MVC 时代相比，组件架构降低耦合、简化测试 |
| **静态类型 + 构建工具链**：TypeScript + Webpack/Vite + Lint 流水线 | 覆盖 80% 的运行时错误减少 — 研究表明类型检查的前端代码生产 Bug 减少 15–40% |

> 组件架构 + 类型化工具链是区分可维护前端与不可维护前端的两个核心杠杆。

---

**A02 UI 设计系统与组件库**（17 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **设计 Token 标准化**：颜色、间距、字体 Token 在设计工具与代码间共享 | 覆盖 80% 的产品一致性问题 — 消除设计师意图与实现 UI 之间的漂移 |
| **带实时示例的组件文档**：Storybook 风格的隔离组件渲染 | 覆盖 80% 的设计系统推广阻力 — 开发者使用他们能预览和隔离测试的组件 |

> 设计 Token + 活文档是将组件库变成真正被采用的设计系统的两个实践。

---

**A03 用户体验（UX）研究与评估**（293 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **混合研究方法**：定性（访谈、出声思维）与定量（任务指标、问卷）结合 | 覆盖 80% 的用户心理模型洞察 — 单一方法无法同时捕获"为什么"和"怎么做" |
| **带用户验证的迭代原型**：在实现前用真实用户测试低保真原型 | 覆盖 80% 的高代价后期重设计 — 论文显示在原型阶段修复 UX 问题比发布后便宜 3–5 倍 |

> 混合方法研究 + 迭代原型验证消除了 UX 返工的最大来源。

---

**A04 可用性测试与启发式评估**（337 篇 — 集群最大类目）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **Nielsen 10 条启发式原则作为结构化检查清单**：系统性检查可见性、反馈、防错、一致性 | 覆盖 80% 的可发现可用性问题 — 研究表明 5 名专家评估者能发现 75% 的问题 |
| **5–8 名真实用户的基于任务测试**：在真实场景中观察真实目标用户完成任务 | 覆盖 80% 的关键可用性失败 — 5 名用户的可用性测试发现约 85% 的主要问题（Nielsen 递减回报定律） |

> 启发式评估廉价发现问题；真实用户任务测试验证并排优先级。

---

**A05 人机交互（HCI）**（55 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **Fitts 定律 + 示能设计**：交互目标的尺寸和距离优化，结合视觉示能提示 | 覆盖 80% 的交互速度和错误率改善 — 触屏和鼠标界面效率的基础原理 |
| **情境调研与情境化用户研究**：在真实工作环境而非实验室中观察用户 | 覆盖 80% 的"实验室验证但现实失效"界面差距 |

> 物理交互原理 + 真实情境研究使 HCI 设计根植于真实人类行为。

---

**A06 无障碍与包容性设计**（45 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **WCAG 2.1 AA 合规作为基线**：语义化 HTML、ARIA 角色、足够色彩对比度、键盘可导航 | 覆盖 80% 的法律无障碍要求及四类主要残障（视觉、运动、听觉、认知）的用户需求 |
| **CI 流水线中的自动化无障碍测试**：每次 PR 运行 axe-core、Pa11y 或 Lighthouse | 覆盖 80% 的可自动检测违规 — 持续门控在发布前捕获回退 |

> WCAG 合规 + CI 自动化门控使无障碍成为持续的工程实践，而非事后审计。

---

**A07 桌面与原生应用开发**（32 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **平台 UI 规范遵循**：macOS HIG / Windows Fluent Design / GNOME HIG 的原生体验感 | 覆盖 80% 的用户采用阻力 — 用户拒绝违反平台约定的应用，即使功能等效 |
| **Electron/Tauri 跨平台 vs 原生性能敏感型应用的架构选择** | 覆盖 80% 的权衡空间 — Web 技术框架牺牲约 30% 内存/CPU；原生在启动时间和电池上占优 |

> 平台规范遵循 + 正确的框架选择（跨平台 vs 原生）决定桌面应用成败。

---

**A08 移动应用开发**（247 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **离线优先架构 + 同步**：本地优先数据模型 + 后台同步，覆盖 80% 的移动网络边缘情况 | 覆盖 80% 的移动端特有可靠性问题 — 移动用户遭遇连接中断是桌面应用从未面对的 |
| **性能预算强制执行**：启动时间 <2s、帧率 60fps、APK/IPA 包体积严格限制 | 覆盖 80% 的应用商店评分驱动因素 — 启动时间和流畅度是用户反馈的前两大性能关注点 |

> 离线优先架构 + 性能预算解决了两个最难的移动端特有工程约束。

---

### 集群 B：软件架构与设计

**B01 软件架构与设计模式**（145 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **关注点分离（六边形/洁净架构）**：领域逻辑与基础设施和展示层隔离 | 覆盖 80% 的可测试性和可维护性收益 — 论文一致显示清晰分层系统的测试和修改工作量减少 40–60% |
| **架构决策记录（ADR）**：记录架构选择的背景、决策和后果的轻量文档 | 覆盖 80% 的团队更迭时的知识损失 — ADR 防止已解决决策被反复讨论，加速新成员融入 |

> 清晰的关注点分离 + 决策理由文档是两个最高杠杆的架构投资。

---

**B02 微服务与面向服务架构**（170 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **基于 DDD 限界上下文的服务边界设计**：限界上下文映射到服务边界，防止"闲聊式"耦合 | 覆盖 80% 的微服务迁移失败 — 服务边界切错导致紧耦合，使微服务的目的失败 |
| **分布式追踪 + 服务网格可观测性**：跨服务 OpenTelemetry 追踪，服务网格流量管理 | 覆盖 80% 的微服务运维复杂性 — 没有跨服务追踪，分布式系统的延迟和故障调试变得难以解决 |

> 正确的服务边界 + 完整可观测性是微服务成功的关键因素。

---

**B03 分布式系统与云原生工程**（50 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **基于 CAP 定理的一致性模型选择**：根据领域需求在强一致性和最终一致性之间做出明确选择 | 覆盖 80% 的分布式系统正确性问题 — 大多数分布式 Bug 源于错误的一致性假设 |
| **基础设施即代码（IaC）**：Terraform/Pulumi/CDK 实现可重现、版本控制的基础设施 | 覆盖 80% 的"我本地没问题"环境漂移问题，并通过重新 apply 实现灾难恢复 |

> 一致性模型清晰 + IaC 消除了两类最常见的分布式系统故障模式。

---

**B04 API 设计与集成模式**（59 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **API 优先设计（OpenAPI/AsyncAPI 契约）**：实现前先定义契约，与消费方共享实现并行开发 | 覆盖 80% 的集成阻力 — 契约优先 API 支持前后端并行开发和消费方驱动契约测试 |
| **版本化策略 + 向后兼容性**：URL 版本化或 Header 版本化，附带弃用策略 | 覆盖 80% 的 API 生命周期管理问题 — 无版本的破坏性变更是集成层中断的首要原因 |

> 契约优先设计 + 规范版本化是影响下游最大的两个 API 实践。

---

**B05 数据库设计与数据访问模式**（460 篇 — 集合最大类目）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **范式化 + 战略性反范式化**：为写入正确性范式化，为读取性能选择性反范式化 | 覆盖 80% 的数据库性能和一致性问题 — 范式化/反范式化权衡是核心数据库设计决策 |
| **仓储模式 + 查询优化纪律**：通过仓储抽象数据访问；分析并优化 N+1 查询和缺失索引 | 覆盖 80% 的应用层数据库性能问题 — N+1 查询和缺失索引是慢查询事故的大多数原因 |

> Schema 设计正确性 + 查询访问模式纪律决定系统全生命周期的数据库层质量。

---

### 集群 C：代码质量与工程实践

**C01 代码质量与静态分析**（145 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **CI 中的自动化 Lint + 风格强制**：ESLint、Pylint、Checkstyle 在每次提交时运行，违规阻断合并 | 覆盖 80% 的代码风格不一致和常见 Bug 模式 — 自动化门控消除格式和明显错误的整类评审意见 |
| **复杂度指标作为合并门控**：圈复杂度阈值（如 >10 触发强制重构） | 覆盖 80% 的最易产生 Bug 的代码 — 高圈复杂度是实证研究中缺陷密度最强的单一预测因子 |

> 自动化质量门控 + 复杂度阈值将质量执行左移，降低评审负担和缺陷率。

---

**C02 技术债与代码坏味道**（118 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **带明确成本的技术债台账**：记录债务条目及预计修复工作量和业务影响，而非仅"我们应该修复它" | 覆盖 80% 的失控债务积累 — 量化债务的团队做出有意权衡；不量化的团队静默积累债务直到阻塞交付 |
| **童子军规则 + 专项债务 Sprint**：在功能工作期间机会性修复小问题；每季度安排专项债务清减 | 覆盖 80% 的"债务永远还不上"问题 — 双轨制方法防止"全是债务"的瘫痪和"从不碰债务"的积累 |

> 明确的债务追踪 + 排期偿还是防止技术债成为生存危机的两个实践。

---

**C03 重构与软件演进**（34 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **测试覆盖作为重构前提**：在没有充分测试覆盖的情况下永远不重构 — 测试是安全网 | 覆盖 80% 的重构引入的回退 — 最常见的重构失败发生在没有测试捕获行为变化时 |
| **Strangler Fig 模式用于遗留系统迁移**：在路由层后面增量替换遗留组件，而非大爆炸重写 | 覆盖 80% 的大规模重构风险 — 大爆炸重写的失败率为 2:1；Strangler Fig 迁移成功率高得多 |

> 测试覆盖 + 增量迁移模式使大规模重构可以存活。

---

**C04 程序理解与代码阅读**（50 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **有意义的命名 + 自文档化代码**：函数和变量名表达意图而非实现 | 覆盖 80% 的代码理解时间 — 研究显示开发者 60% 的代码阅读时间花在命名歧义消解上 |
| **代码库内一致的结构和模式**：错误处理、日志、模块组织遵循既定约定 | 覆盖 80% 的新成员上手时间 — 模式一致性让开发者预测结构而非发现结构 |

> 有意识的命名 + 结构一致性是代码理解最高杠杆的两个投资。

---

**C05 代码评审与协作开发**（106 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **小而专注的 PR（<400 行）+ 清晰描述**：评审者能有效评估小 PR；大 PR 被走过场 | 覆盖 80% 的评审质量 — 研究显示评审效果在 400 行以上急剧下降；评审者在大 Diff 中发现的 Bug 比例更低 |
| **涵盖安全、正确性和设计的评审检查清单**：结构化评审覆盖风格之外，捕获设计和安全问题 | 覆盖 80% 的代码评审价值（超越风格执行）— 非结构化评审遗漏检查清单能捕获的安全和正确性问题 |

> 小 PR + 结构化检查清单最大化代码评审的缺陷检测价值。

---

### 集群 D：需求与开发过程

**D01 需求工程与需求获取**（200 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **结构化需求模板（用户故事 + 验收标准）**：每个故事有 Given/When/Then 完成定义 | 覆盖 80% 的需求歧义 — 验收标准迫使干系人在开工前明确说明"完成"的含义 |
| **需求可追溯性矩阵**：将需求关联到实现物和测试用例 | 覆盖 80% 的范围蔓延和功能遗漏风险 — 可追溯性使缺口和未测试需求可见 |

> 故事级验收标准 + 需求到测试的追溯性消除了需求失败的两大主要来源。

---

**D02 敏捷、Scrum 与精益开发**（70 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **带可操作成果的 Sprint 回顾**：每次回顾产出 1–3 个团队承诺落地的具体过程改进 | 覆盖 80% 的团队过程改进 — 没有承诺的回顾是没有学习的事后分析；承诺行动项驱动可测量改进 |
| **Sprint 边界强制执行完成定义（DoD）**：每个条目必须满足团队商定的明确标准才能标记为完成 | 覆盖 80% 的"完成但未完成"技术债积累 — 没有强 DoD 的团队定期交付不完整工作，之后以 Bug 形式返回 |

> 承诺的回顾行动 + 强制执行的 DoD 是与结果相关性最高的两个敏捷实践。

---

**D03 CI/CD 与发布工程**（54 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **快速反馈流水线（<10 分钟红绿）**：将 CI 流水线保持在 10 分钟以内以维持开发者心流 | 覆盖 80% 的 CI 采用率 — 超过 15 分钟的流水线会被禁用或绕过；快速流水线才会被真正使用 |
| **带自动回滚的部署流水线**：灰度部署 + 错误率触发自动回滚 | 覆盖 80% 的部署风险 — 自动回滚将部署引入的中断从"小时级发现"转变为"分钟级发现并解决" |

> 快速流水线 + 自动回滚是推动部署信心和频率的两个 CI/CD 实践。

---

**D04 DevOps 与平台工程**（22 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **带自服务能力的内部开发者平台（IDP）**：开发者无需开运维工单即可供应环境和部署 | 覆盖 80% 的 DevOps 采用障碍 — DevOps 失败的首要原因是开发者仍依赖运维工单处理日常工作 |
| **黄金路径模板**：预配置的项目模板，内置 CI/CD、可观测性和安全 | 覆盖 80% 的入职和一致性问题 — 黄金路径将新项目搭建从数天缩短到数小时，并自动执行标准 |

> 自服务平台 + 黄金路径模板消除使 DevOps 转型停滞的协调开销。

---

### 集群 E：开发者体验与生产力

**E01 开发者生产力与体验**（15 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **心流状态保护**：最小化中断、异步优先沟通、核心工作时间无会议保护 | 覆盖 80% 的深度工作容量 — 研究表明一次打断需要 23 分钟恢复时间；保护心流成倍提升产出 |
| **快速本地开发反馈循环**：热重载、30 秒内完成本地测试、本地环境与生产对等 | 覆盖 80% 的开发者满意度调查中的生产力阻碍 — 本地迭代缓慢是被引用最多的生产力阻碍 |

> 心流保护 + 快速本地反馈是最直接影响开发者产出和满意度的两个杠杆。

---

**E02 AI 辅助软件开发**（148 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **LLM 用于样板代码和脚手架生成**：用 AI 生成 CRUD 端点、测试桩、配置文件、文档草稿 | 覆盖 80% 的 AI 编程工具可测量生产力提升 — 研究表明样板代码节省约 30–40% 时间，但在新颖算法工作上几乎无提升 |
| **AI 生成代码的人工验证循环**：将 AI 输出视为需要评审的初稿，而非完成品 | 覆盖 80% 的 AI 引入 Bug — 未经评审的 AI 代码引入通过语法检查但业务逻辑错误的细微问题 |

> AI 擅长样板代码；人工负责验证 — 组合使用在不降低质量的情况下获取生产力提升。

---

**E03 开源与社区开发**（373 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **CONTRIBUTING.md + Issue 模板 + PR 模板**：告知贡献者如何参与的结构化入门文档 | 覆盖 80% 的首次贡献者流失 — 没有明确贡献指南的项目在"如何开始？"这一步流失大多数潜在贡献者 |
| **响应式维护者（PR 评审 <7 天）**：及时反馈是贡献者留存的最强预测因子 | 覆盖 80% 的贡献者流失 — 贡献者停止贡献的最常见原因是缺乏维护者响应 |

> 贡献基础设施 + 响应式维护者是决定开源项目健康度的两个可控因素。

---

### 集群 F：安全工程

**F01 应用安全工程**（35 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **设计阶段威胁建模（STRIDE/DREAD）**：在编写代码前系统性识别威胁 | 覆盖 80% 的架构安全漏洞 — 威胁建模发现的问题比部署后发现便宜 100 倍 |
| **OWASP Top 10 作为强制评审检查清单** | 覆盖 80% 的 Web 应用被利用漏洞 — OWASP Top 10 占真实世界漏洞的大多数 |

> 设计阶段威胁建模 + OWASP Top 10 门控系统性覆盖架构和实现层安全。

---

**F02 漏洞检测与分析**（81 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **CI 流水线中的 SAST + DAST**：静态分析（Semgrep/CodeQL）发现代码级漏洞；动态分析（OWASP ZAP）发现运行时问题 | 覆盖 80% 的可自动检测漏洞 — 静态和动态扫描结合覆盖代码级和部署级安全问题 |
| **依赖漏洞扫描（SCA）**：每次构建运行 Dependabot、Snyk 或 OWASP Dependency-Check | 覆盖 80% 的供应链攻击面 — 现代应用漏洞的大多数来自依赖，而非第一方代码 |

> SAST/DAST 自动化门控 + 依赖扫描是两个最高覆盖率的自动化安全控制。

---

**F03 隐私工程与合规**（15 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **设计时数据最小化**：仅收集功能严格必要的数据；默认不记录 PII | 覆盖 80% 的隐私风险面 — 不收集的数据无法被泄露、滥用或受监管行动约束 |
| **新功能隐私影响评估（PIA）**：发布前审查数据流、保留和访问控制 | 覆盖 80% 的 GDPR/CCPA 合规缺口 — PIA 在事故发生前捕获数据处理违规 |

> 最小化数据收集 + 发布前隐私评审是防止隐私债积累的两个实践。

---

**F04 认证、授权与身份管理**（12 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **多因素认证（MFA）+ 抗网络钓鱼凭证**：特权访问最低要求 FIDO2/WebAuthn 或 TOTP | 覆盖 80% 的账户接管攻击向量 — 凭证填充和网络钓鱼是认证漏洞的大多数原因 |
| **最小特权原则 + RBAC**：仅授予特定角色所需权限；每季度审计并撤销未使用权限 | 覆盖 80% 的授权相关漏洞 — 过度授权账户是数据漏洞的第二大原因（仅次于凭证泄露） |

> MFA + 最小特权 RBAC 共同解决认证和授权两个攻击面。

---

**F05 软件供应链安全**（10 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **SBOM 生成 + 依赖溯源验证**：每次发布的软件物料清单；验证包校验和 | 覆盖 80% 的供应链攻击可检测性 — SBOM 在新 CVE 发布时能快速识别受影响组件 |
| **锁定依赖版本 + 自动更新 PR**：锁定版本；用 Dependabot/Renovate 自动化安全更新 | 覆盖 80% 的依赖混淆和版本漂移攻击 — 锁版本防止意外更新；自动化 PR 保持依赖最新 |

> SBOM 可见性 + 自动化依赖管理是供应链安全的两个基础。

---

### 集群 G：性能与可靠性

**G01 性能工程与性能分析**（31 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **先分析再优化 — 量化而非猜测**：用火焰图和分析器数据识别真实瓶颈 | 覆盖 80% 的优化工作浪费 — 实证研究显示开发者对性能瓶颈的直觉超过 70% 是错的 |
| **带自动回退检测的性能预算**：定义延迟/吞吐量 SLO；性能回退超过阈值时 CI 失败 | 覆盖 80% 的到达生产的性能退化 — 没有自动基线，性能退化是不可见的 |

> 数据驱动的分析 + 自动化性能门控防止性能工程的两大主要失败模式。

---

**G02 可观测性、监控与日志**（10 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **可观测性三支柱（指标+日志+追踪）通过 Trace ID 关联**：将单个请求的日志、Span 和指标联系起来 | 覆盖 80% 的分布式系统可调试性 — 有关联遥测的团队在分钟内解决事故；没有的团队花数小时重建 |
| **带一致 Schema 的结构化日志**：带一致字段（时间戳、服务、trace_id、级别、消息、错误）的 JSON 日志 | 覆盖 80% 的日志搜索和告警效率 — 结构化日志支持无正则过滤和错误字段自动告警 |

> 关联的可观测性三支柱 + 结构化日志是可靠运营分布式系统的最低要求。

---

### 集群 H：AI 与软件哲学

**H01 LLM 与软件工程**（69 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **LLM 作为代码解释和文档工具**：用 LLM 解释陌生代码、生成文档字符串、总结 PR | 覆盖 80% 的低风险高价值 LLM 应用 — 解释任务不需要正确性保证，所以 AI 错误对人类读者立即可见 |
| **所有 LLM 生成代码必须人工评审**：无 AI 生成代码未经人工评审进入生产；将 AI 输出作为起点 | 覆盖 80% 的 AI 引入缺陷风险 — "看起来正确"但有细微语义错误的 LLM 代码是 AI 辅助 SE 的首要质量问题 |

> LLM 作为解释工具 + 强制人工评审最大化生产力/质量权衡。

---

**H02 软件哲学、美学与设计品味**（30 篇）

| 关键杠杆（20%） | 覆盖效果（80%） |
|----------------|----------------|
| **简洁作为一等设计目标**：抵制在不需要时添加功能、抽象和选项（YAGNI、Unix 哲学） | 覆盖 80% 的变得不可维护的软件 — 复杂性是增量积累的；简洁需要主动抵制"顺手加"的冲动 |
| **设计品味是可学习的技能**：研究设计良好的系统（Unix 工具、SQLite、Redis）以内化好的接口和架构设计原则 | 覆盖 80% 的"能用的软件"和"能持久的软件"之间的差距 — 品味通过接触好作品来培养，而非仅仅避免坏实践 |

> 主动的简洁纪律 + 接触优秀设计是培养软件品味的两个实践。

---

## 关键横切发现

### 发现 1：数据库复杂性是最主要的研究课题
460 篇论文——数据库设计和数据访问模式远超其他类目。现代应用的状态管理复杂性（从关系型到文档型到图型到向量存储）是语料库中反映的首要工程挑战。

### 发现 2：开源工程已成为一个独立领域
373 篇关于 OSS 实践的论文表明，维护开源项目是一个被认可的工程学科，研究领域包括贡献者留存、公交车因子、社区健康和治理模型。

### 发现 3：AI 辅助开发是增长最快的领域
148 篇 AI 辅助开发论文几乎全部来自 2023–2026 年，呈急剧上升趋势。这是该领域增长最快的研究方向。2023 年前，该类目的论文几乎不存在。

### 发现 4：安全和隐私的学术研究相对工业实践严重不足
尽管是工业界最关注的领域，应用安全（35 篇）、供应链安全（10 篇）和隐私工程（15 篇）的学术覆盖却很稀疏。这些领域的工业知识显著超前于学术发表。

### 发现 5：软件哲学重新兴起
30 篇关于软件设计哲学和美学的论文代表了对软件工程"工艺"维度的兴趣复苏——简洁、优雅和设计品味作为职业价值观。

---

[English README](README.md) | [知识文档](sw-engineering.md) | [返回主目录](../README.md)

---

## Paradigm Shifts / 范式转移 (Kuhn)

```
OLD PARADIGM                    Trigger Event                   NEW PARADIGM
─────────────────────          ─────────────────────          ─────────────────────
Waterfall testing               Agile / XP (2001)             Shift-left, continuous testing
  │ test after code is done         │ TDD, fast iteration          │ quality is built-in, not bolted-on
  └──────────────────────────────── ┘                             │
                                                                   │
Manual regression suites        CI/CD pipelines (2010s)       Automated test-in-pipeline
  │ run before release                │ every commit triggers tests  │ testing is infrastructure
  └──────────────────────────────────┘                             │
                                                                   │
Code coverage as quality proxy  Mutation testing research      Outcome-based quality metrics
  │ 100% coverage = safe              │ mutation score / DORA         │ MTTR, change failure rate
  └──────────────────────────────────┘
```

**已被推翻的认知误区:**
- ✗ "测试是编码完成后的阶段" → TDD/BDD证明测试是设计活动
- ✗ "100%代码覆盖率保证正确性" → 变异测试揭示覆盖率的局限
- ✗ "E2E测试是质量的黄金标准" → 测试金字塔证明单元测试为主的底层结构更优

