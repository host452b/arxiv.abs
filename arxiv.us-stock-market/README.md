# arxiv.us-stock-market

A curated collection of academic papers on **US stock market investment analysis**, organized by 3-year investment cycle stages. Applies 80/20 Pareto analysis to identify the 20% of core factors that drive 80% of returns and win-rate, classified across different analytical layers.

- **Time span**: 2010–2026
- **Total unique papers**: 1,241
- **Search files**: 24 topic searches
- **Cycle stages**: 5 investment cycle stages × 3-year intervals
- **Primary source**: arXiv Quantitative Finance (q-fin)

---

## Investment Cycle Stage Overview

US stock market cycles historically average 3–7 years peak-to-peak. The 3-year bracket captures one full average business cycle phase.

| Stage | Market Environment | Typical Duration | Key Driver |
|-------|-------------------|-----------------|------------|
| C01 | **Accumulation** (Early Bull) | 1–2 years | Institutional re-entry, cheap valuations |
| C02 | **Expansion** (Mid Bull) | 2–4 years | Earnings growth, momentum, sector rotation |
| C03 | **Distribution** (Late Bull) | 1–2 years | Valuation stretch, sentiment peaks |
| C04 | **Contraction** (Bear Market) | 1–2 years | Macro deterioration, volatility spike |
| C05 | **Recovery** (Early Cycle Turn) | 1–2 years | Policy pivot, value emergence |

---

## 80/20 Analysis by Analytical Layer

### Layer 1 — Macro-Economic Factors

**20% Key Drivers → 80% of Market Direction**

| Rank | Factor | Predictive Horizon | Papers |
|------|--------|-------------------|--------|
| 1 | **Interest rate cycle** (Fed policy) | 6–24 months | 199 |
| 2 | **Inflation / real yield environment** | 6–18 months | 127 |
| 3 | **Business cycle phase** (leading indicators) | 3–12 months | 46 |
| 4 | **Equity risk premium** (ERP) | 12–36 months | 143 |
| 5 | **Credit spreads** (default risk signal) | 3–9 months | — |

**Research consensus**: Interest rate direction explains ~40% of equity market direction at a 12-month horizon. The Fed Funds rate cycle is the single most monitored macro variable in institutional equity strategy.

---

### Layer 2 — Market Timing & Cycle Indicators

**20% Key Signals → 80% of Cycle-Timing Accuracy**

| Rank | Signal | Type | Reliability |
|------|--------|------|-------------|
| 1 | **Yield curve** (2yr–10yr spread) | Leading indicator | High (recession ~12m out) |
| 2 | **Market regime detection** (HMM, rolling volatility) | Statistical | Medium-High |
| 3 | **Volatility regime** (VIX > 25 = fear zone) | Sentiment-based | High for short-term |
| 4 | **Momentum signals** (12-1 month momentum) | Cross-sectional | Medium |
| 5 | **Sector rotation patterns** | Cyclical | Medium |

| Old Paradigm | Trigger Event | New Paradigm |
|---|---|---|
| **CAPM single-factor model** — beta explains all returns | Fama-French (1992): size and value anomalies | **Multi-factor risk models** — 5-factor + momentum premia |
| **Efficient Market Hypothesis** — prices fully reflect all information | Shiller / behavioral finance: excess volatility puzzle | **Factor premia + behavioral biases** — PEAD, momentum, and value persist |
| **Constant volatility (Black-Scholes)** — σ is a fixed parameter | GARCH / stochastic vol models (1986+): Engle, Heston | **Regime-switching volatility** — vol clusters and mean-reverts over time |
| **Fundamental analysis only** — DCF, P/E, analyst calls | Quant revolution (1980s–): Simons, Asness, Fama | **Systematic / factor investing** — risk premia harvested with discipline |

**已被推翻的认知误区 / Overturned Beliefs:**
- ✗ "技术分析是金融占星术" → 数学分析表明移动平均策略在特定机制条件下具有正期望值
- ✗ "比特币是'数字黄金'，对冲通胀" → 多篇论文证实比特币与通胀冲击呈负相关或零相关；它是风险资产
- ✗ "均值方差优化可靠地产生最优投资组合" → 预期收益的估计误差使MVO对输入极为敏感；贝叶斯/鲁棒方法更优
- ✗ "市场收益在时间上同分布" → 机制转换模型表明牛市/熊市阶段的收益均值和方差在统计上不同

