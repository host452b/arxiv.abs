# arxiv.us-stock-market

聚焦**美股市场投资逻辑分析**的学术论文集合，以 3 年为一个档位划分投资周期阶段，应用二八定律提炼关键杠杆（20% 核心因子 → 80% 收益/胜率），并按照不同分析层次分类。

- **时间范围**：2010–2026
- **去重论文总量**：1,241 篇
- **检索文件**：24 个主题搜索
- **周期阶段**：5 个投资周期阶段 × 3 年一档
- **主要来源**：arXiv 量化金融（q-fin）

---

## 投资周期阶段总览

美股市场周期历史平均 3–7 年（峰谷到峰谷）。以 3 年为一档可覆盖一个完整的平均商业周期阶段。

| 阶段 | 市场环境 | 典型持续时间 | 核心驱动 |
|------|---------|------------|---------|
| C01 | **积累期**（牛市初期） | 1–2 年 | 机构重新入场、估值低廉 |
| C02 | **扩张期**（牛市中期） | 2–4 年 | 盈利增长、动量、轮动 |
| C03 | **分配期**（牛市末期） | 1–2 年 | 估值拉伸、情绪见顶 |
| C04 | **收缩期**（熊市） | 1–2 年 | 宏观恶化、波动率飙升 |
| C05 | **复苏期**（周期底部转折） | 1–2 年 | 政策转向、价值重现 |

---

## 按分析层次的二八定律

### 第一层 — 宏观经济因子

**20% 关键驱动 → 80% 市场方向**

| 排名 | 因子 | 预测周期 | 相关论文数 |
|------|------|---------|----------|
| 1 | **利率周期**（美联储政策） | 6–24 个月 | 199 |
| 2 | **通胀/实际收益率** | 6–18 个月 | 127 |
| 3 | **商业周期阶段**（领先指标） | 3–12 个月 | 46 |
| 4 | **股权风险溢价**（ERP） | 12–36 个月 | 143 |
| 5 | **信用利差**（违约风险信号） | 3–9 个月 | — |

**研究共识**：利率方向在 12 个月维度上解释约 40% 的股市走向。联邦基金利率周期是机构股票策略中监测频率最高的单一宏观变量。

---

### 第二层 — 市场择时与周期信号

**20% 核心信号 → 80% 周期判断准确率**

| 排名 | 信号 | 类型 | 可靠性 |
|------|------|------|--------|
| 1 | **收益率曲线**（2年-10年利差） | 领先指标 | 高（预测衰退约领先 12 个月） |
| 2 | **市场机制识别**（HMM、滚动波动率） | 统计模型 | 中高 |
| 3 | **波动率机制**（VIX > 25 = 恐慌区） | 情绪指标 | 短线高 |
| 4 | **动量信号**（12-1 个月动量） | 横截面 | 中 |
| 5 | **行业轮动模式** | 周期性 | 中 |

```
商业周期 → 行业轮动地图：
  周期初期：金融、可选消费、工业
  周期中期：科技、材料、能源
  周期末期：能源、医疗、必选消费
  衰退期：必选消费、医疗、公用事业
```

---

### 第三层 — 选股因子

**20% 核心因子 → 80% 超额收益**

**法马-弗伦奇五因子模型**（学术共识）：
| 因子 | 描述 | 长期溢价 |
|------|------|---------|
| **市场（MKT）** | 股权风险溢价 | ~5–7%/年 |
| **规模（SMB）** | 小盘 vs. 大盘 | ~2%（2000年后有争议） |
| **价值（HML）** | 低 vs. 高市净率 | ~3%（周期性） |
| **盈利能力（RMW）** | 高 vs. 低净资产收益率 | ~3% |
| **投资风格（CMA）** | 保守 vs. 激进资本支出 | ~2% |

**动量因子**（Jegadeesh & Titman, 1993）：
- 过去 12 个月减去最近 1 个月的收益率预测未来 3–12 个月收益
- 效应量：约 6–10%/年（但存在崩溃风险）

**二八定律洞察**：在任何滚动 3 年期间，5 个因子中只有 2–3 个同时"有效"。因子投资需要结合周期意识。

---

### 第四层 — 风险管理

**20% 核心操作 → 80% 的回撤控制效果**

```
组合风险管理层级：
  1. 仓位规模控制（凯利公式/分数凯利）
     → 防止单一仓位破产
  2. 单股止损纪律
     → 控制每个仓位的最大亏损
  3. 组合波动率目标化
     → 高波动期自动降仓
  4. 最大回撤规则
     → 触及最大回撤阈值 → 降低风险敞口
  5. 跨不相关因子分散
     → 因子动物园：各因子并非同步运动
```

**波动率管理组合**（Moreira & Muir, 2017）：
- 根据实现波动率反向调整股票敞口
- 改善股票、动量和价值策略的夏普比率

---

### 第五层 — 行为金融因子

**20% 核心偏差 → 80% 散户投资者跑输市场**

| 偏差 | 描述 | 影响 |
|------|------|------|
| **过度自信** | 高估技能、低估风险 | 年化 -2% 至 -5% |
| **损失厌恶** | 损失感受是收益的 2 倍 | 过早卖出赢家、死守亏损 |
| **近因偏差** | 过度重视近期事件 | 追涨杀跌 |
| **处置效应** | 卖赢家、持亏家 | 税务低效、拖累绩效 |
| **本地偏见** | 过度集中国内/熟悉股票 | 分散化不足 |

**DALBAR 研究**：2003–2023 年，平均股票基金投资者年化约 3.9% vs. 标普 500 年化约 10.3%，差距主要来自行为择时错误。

---

### 第六层 — 量化/系统化策略

**20% 核心模型 → 80% 系统化超额收益**

| 策略类型 | 优势来源 | 时间维度 |
|---------|---------|---------|
| **趋势跟踪/CTA** | 动量持续性 | 1–12 个月 |
| **统计套利** | 均值回复、相关性 | 天–周 |
| **因子投资** | 风险溢价收割 | 1–5 年 |
| **机器学习预测** | 非线性模式挖掘 | 中短期 |
| **期权/波动率策略** | 方差风险溢价（VRP） | 月度 |

---

## 分周期阶段二八定律详解

### C01 — 积累期（牛市初期）

**市场特征**：危机/熊市后的底部，估值低廉，市场悲观，机构开始悄悄建仓

**二八策略**：
1. **深度价值 + 质量筛选** — 无人问津时买入便宜且 ROE 高的公司
2. **宽基指数配置** — 复苏第一阶段，高 β 策略回报丰厚
3. **信用修复信号** — 高收益利差收窄确认宏观底部

**学术支撑**：股权风险溢价历史高位时 → 未来 5 年正回报强（Damodaran 研究系列）

---

### C02 — 扩张期（牛市中期）

**市场特征**：GDP 增长，盈利扩张，利率初期上升，动量主导

**二八策略**：
1. **动量 + 质量** — 顺势而为，用盈利能力过滤
2. **行业轮动** — 科技、工业、材料领涨
3. **因子敞口** — 盈利能力（RMW）和投资风格（CMA）因子活跃期

---

### C03 — 分配期（牛市末期）

**市场特征**：估值峰值，增长放缓，收益率曲线趋平/倒挂，情绪极度乐观

**二八策略**：
1. **降低 β，提高质量** — 向防御性板块倾斜
2. **监控收益率曲线** — 倒挂是最可靠的衰退信号
3. **对冲波动率** — VIX 期权或防守型期权策略

---

### C04 — 收缩期（熊市）

**市场特征**：EPS 恶化，加息达峰，波动率 > 25，回撤超过 20%

**二八策略**：
1. **风险规避：增加现金或对冲** — 波动率目标化管理
2. **短线交易策略** — 高波动率创造短线动量机会
3. **信用利差扩大信号** — 更深度衰退的领先信号

**研究支撑**：高波动率机制下，短线交易异常效应放大（论文：200篇短线交易、200篇波动率）

---

### C05 — 复苏期（周期底部转折）

**市场特征**：政策转向（降息），估值受压，动量开始早期反转

**二八策略**：
1. **利率敏感型板块** — 金融、房地产受益于降息
2. **小盘股倾斜** — 历史上在周期转折点显著跑赢
3. **预期收益窗口** — 此时 12 个月前瞻股权风险溢价最高

---

## 检索文件索引

| 文件 | 主题 | 论文数 | 周期 | 论文观点 / 结论 / 推荐做法 | 被推翻的理论 / 既定谬误 |
|---|---|---|---|---|---|
| 01-momentum.json | 价格动量 | 2 | C02 | 动量效应真实存在，但**因市场子域而异**——在不同市值分层或指数子集中表现不均匀，不可盲目套用。可用物理学"速度×质量"框架量化动量强度。**推荐**：做动量筛选前先过滤流动性，小市值低流动性股票的动量易失真。 | "Momentum investing is speculation with no theoretical basis" → Three-factor and five-factor models now include momentum as a systematic risk premium. |
| 02-technical-analysis.json | 技术分析 | 23 | 全周期 | 移动平均等技术指标可在特定动态假设下用**对数效用最优化**证明其合理性，与半强有效市场并不矛盾。价格"速度+加速度"比滞后型指标更稳健。支撑/阻力位可建模为最优停止问题。**推荐**：技术分析用于择时而非选股；单独使用无超额收益，结合基本面或机制判断才有效。 | "Technical analysis is financial astrology" → Mathematical analysis shows moving-average strategies have positive expected returns in specific regime conditions. |
| 03-short-term-trading.json | 短线交易策略 | 200 | C04, C02 | 交易冲击（Price Impact）在各市场具有**普适规律**，与资产类别无关。LSTM/深度学习显著优于经典统计模型预测短期价格。Twitter/Reddit情绪信号可预测短期反转。高波动环境下的交易暂停后，买卖价差异常扩大，存在可利用的微观结构效应。**推荐**：将LSTM与情绪信号融合；高频环境下必须将市场冲击纳入策略成本。 | "Markets always process information instantly (weak-form EMH)" → Microstructure research shows predictable short-term price impact patterns universal across assets. |
| 04-earnings.json | 盈利公告与超预期 | 7 | C02, C03 | **盈利公告后漂移（PEAD）持续存在**——价格在公告后数周仍沿惊喜方向运动。散户持仓周期决定其对盈利的反应模式。财报文本用LLM嵌入后能有效预测当天涨跌方向。期权隐波在EA前飙升、后骤降（"波动率挤压"）。**推荐**：用LLM解析财报文本判断惊喜方向，持有3–5个交易日捕捉PEAD收益。 | "Earnings surprises are fully priced in at announcement" → Post-Earnings Announcement Drift (PEAD) persists for weeks; EMH contradicted. |
| 05-fundamental-value.json | 基本面/价值投资 | 20 | C01 | 多因子ML模型（436+特征）显著优于单一估值比率筛选。卖方分析师报告经LLM嵌入后含有可量化的超额收益信息。**系统化价值投资可被建模为优化问题**，优于主观判断。VaR约束的均值-方差配置在尾部风险下更稳健。**推荐**：量化评分与LLM解析的文件结合使用；价值因子在周期底部（C01）配置效果最佳。 | "Value investing is simply buying low P/B stocks" → Junk-factor contamination: quality screens are required to separate cheap quality from cheap junk. |
| 06-business-cycle.json | 商业周期指标 | 46 | 全周期 | 商业周期具有**内生性**——股市动态与实体经济互为耦合，而非纯粹外生冲击被动响应。油价冲击与利率冲击是主要扰动源。各国周期具有跨境同步性。**推荐**：用LEI综合指数（新订单+工时+申请失业金人数+股价）判断周期阶段；阶段判断先于行业轮动决策。 | "Business cycles are purely exogenous shock responses" → Endogenous cycle models show coupled stock-real economy dynamics generate cycles internally. |
| 07-sector-rotation.json | 行业轮动 | 4 | C02 | 因子模型与基本面指标（CPI、GDP阶段）**组合使用**优于单独使用。ML集成方法可根据近期预测准确率动态加权。强化学习智能体在实时轮动决策中展示出潜力。**推荐**：两阶段流程——宏观机制识别 → 行业评分 → 仓位定量；切勿依赖单一宏观信号轮动。 | "Sector rotation is not predictably exploitable" → Business cycle phase → sector return differentials are statistically significant across multiple markets. |
| 08-factor-investing.json | 多因子策略 | 21 | 全周期 | 深度多因子模型可捕捉Fama-French线性模型遗漏的**非线性因子交互**。机制跳变（Regime Switch + Jump）必须建模，否则严重低估尾部风险。**LLM单独无法可靠生成选股预测**，仍需量化或人工监督。**推荐**：持有4–5个因子敞口+机制感知；警惕因子拥挤，动量因子尤其容易出现崩溃。 | "CAPM single-factor model accurately prices equities" → Fama-French research (1992) definitively rejected CAPM; multi-factor models are the empirical consensus. |
| 09-market-regime.json | 市场机制识别 | 42 | 全周期 | 牛/熊/压力机制在统计上**显著不同**，同一策略参数跨机制使用会大幅降效。路径签名（Path Signature）+Wasserstein距离聚类的检测速度优于传统滚动HMM。牛熊转换受股市与实体经济的非对称因果关系驱动。**推荐**：对每个机制分别拟合策略参数；用无监督聚类做客观机制标注，避免事后偏差。 | "Market returns are identically distributed over time" → Regime-switching models show mean and variance of returns are statistically distinct across bull/bear phases. |
| 10-equity-premium.json | 股权风险溢价 | 143 | C01, C05 | ERP最可靠的实时估计来自**SPX期权链的到期结构**（无需强模型假设）。宏观环境剧变（如COVID-19）会造成历史极端ERP读数。规模溢价在控制流动性（美元换手率）后依然存在。**推荐**：监控实时ERP作为入场/退出的长期信号；ERP > 5% 是最强的长期做多信号，此时是C01/C05买入窗口。 | "The equity risk premium is stable and predictable" → ERP varies dramatically across macro regimes; it is a time-varying conditional premium. |
| 11-portfolio.json | 组合优化 | 151 | 全周期 | **数据不完整/不准确时，标准MVO（均值-方差优化）会产生极度集中的脆弱组合**。混合机制预测 + Black-Litterman + 弹性网络正则化构建的多资产组合最稳健。主动vs被动管理可统一为"跟踪误差-超额收益"权衡问题。**推荐**：用风险平价或正则化BL替代原始MVO；按阈值漂移（5%）再平衡，而非按日历时间。 | "Mean-variance optimization reliably produces optimal portfolios" → Estimation error makes MVO extremely sensitive to inputs; Bayesian/robust methods outperform. |
| 12-volatility.json | 波动率建模 | 200 | C04 | **HAR模型**（异质自回归）是已实现波动率预测的学术基准——可捕捉长记忆、不对称和日内模式。图信号处理的网络波动率模型（跨股票）显著提升S&P 500预测精度。宏观关注度+情绪可独立预测未来波动率。杠杆效应（负收益→更高波动率）具有普遍性。**推荐**：以HAR-RV为基准；叠加宏观情绪用于中期波动率目标化；VIX > 25时压缩敞口。 | "Volatility is constant (Black-Scholes constant σ assumption)" → Stochastic volatility (Heston, SABR) and volatility clustering (GARCH) have replaced constant σ. |
| 13-interest-rate.json | 利率与货币政策 | 199 | C03, C05 | Fed政策对利率具有**长程依赖效应**——政策变化在市场中持续数月乃至数年。FOMC的"信息效应"（超越利率决策本身的信号含义）是跨资产波动的主要溢出渠道。货币政策不确定性对加密货币及风险资产有独立影响。**推荐**：将Fed行动分解为"纯利率"与"信号/信息"两类；后者驱动绝大多数短期跨资产波动，需单独建模。 | "Monetary policy affects only the current short rate" → Yield curve research shows monetary policy shifts the entire term structure. |
| 14-inflation.json | 通胀与投资 | 127 | C03 | **比特币不能对冲通胀**（多篇论文确认，与通胀公告负相关）。通胀越来越由国际因素驱动，而非单纯国内需求。金融冲击经由企业资产负债表传导（债务-通胀渠道）。公众注意力阈值触发非线性通胀预期动态——预期比实际数据更重要。**推荐**：用能源/大宗商品和TIPS对冲通胀；避免用加密货币做通胀套保；密切监测通胀预期（断点盈亏平衡率）。 | "Bitcoin is 'digital gold' and hedges inflation" → Multiple papers confirm Bitcoin has negative or zero correlation with inflation shocks. |
| 15-prediction.json | 市场预测模型 | 131 | 全周期 | 股市具有**多重分形结构**，具有时变的可预测性——不是纯随机游走。配备实时网络访问的Agentic LLM在nowcasting股票收益方面展示出初步能力。**可预测性本身不等于盈利能力**——交易成本和容量限制会侵蚀优势。深度学习（LSTM/Transformer）样本内表现好但过拟合风险高。**推荐**：集成ML+严格OOS验证；将可预测性视为衰减信号，需持续更新；回测Sharpe > 2.0 通常是数据挖掘产物。 | "Stock price changes are a random walk (pure EMH)" → Multifractal analysis reveals long-memory and non-random time-varying structure. |
| 23-risk-management.json | 风险管理 | 2 | C04 | **元组合方法（Meta Portfolio Method）**通过ML自适应选择当前机制最优子策略，优于固定权重策略。分形/长记忆风险模型（Fractal Risk Parity）比标准MPT更准确地捕捉真实相关结构。**推荐**：根据已实现机制动态切换策略权重；不要用静态相关矩阵做风险平价——在压力机制下相关性急剧上升。 | "Normal distribution adequately models portfolio returns" → Fat-tailed distributions (Pareto, Student-t) and fractal risk models are empirically superior. |

---

[英文 README](README.md) | [知识文档](us-stock-market.md) | [返回主目录](../README.md)

---

## Paradigm Shifts / 范式转移 (Kuhn)

```
OLD PARADIGM                    Trigger Event                   NEW PARADIGM
─────────────────────          ─────────────────────          ─────────────────────
CAPM single-factor model        Fama-French (1992)            Multi-factor risk models
  │ beta explains all returns        │ size/value anomalies          │ 5-factor + momentum premia
  └──────────────────────────────── ┘                             │
                                                                   │
Constant volatility (BS model)  GARCH / stochastic vol (1986+) Regime-switching volatility
  │ σ is fixed parameter             │ Engle, Heston models          │ vol clusters, mean-reverts
  └──────────────────────────────────┘
```

**已被推翻的认知误区:**
- ✗ "技术分析是金融占星术" → 移动平均策略在特定机制下有正期望值
- ✗ "比特币是对冲通胀工具" → 比特币与通胀冲击呈负相关；它是风险资产
- ✗ "均值方差优化可靠地产生最优投资组合" → 贝叶斯/鲁棒方法更优

