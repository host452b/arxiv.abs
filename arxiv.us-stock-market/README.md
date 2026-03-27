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

```
Business Cycle → Sector Rotation Map:
  Early Cycle:   Financials, Consumer Discretionary, Industrials
  Mid Cycle:     Technology, Materials, Energy
  Late Cycle:    Energy, Healthcare, Consumer Staples
  Recession:     Consumer Staples, Healthcare, Utilities
```

---

### Layer 3 — Stock Selection Factors

**20% Core Factors → 80% of Alpha Generation**

**Fama-French Five-Factor Model** (academic consensus):
| Factor | Description | Long-run Premium |
|--------|-------------|-----------------|
| **Market (MKT)** | Equity risk premium | ~5–7% annually |
| **Size (SMB)** | Small vs. Large cap | ~2% (disputed post-2000) |
| **Value (HML)** | Low vs. High P/B | ~3% (cyclical) |
| **Profitability (RMW)** | High vs. Low ROE | ~3% |
| **Investment (CMA)** | Conservative vs. Aggressive capex | ~2% |

**Momentum Factor** (Jegadeesh & Titman, 1993):
- 12-month-minus-1-month past return predicts next 3–12 month return
- Effect size: ~6–10% annually (but with crash risk)

**80/20 insight**: In any 3-year rolling period, only 2–3 of the 5 factors are "on" simultaneously. Factor investing requires cycle awareness.

---

### Layer 4 — Risk Management

**20% Practices → 80% of Drawdown Reduction**

```
Portfolio Risk Hierarchy:
  1. Position sizing (Kelly Criterion / fractional Kelly)
     → Prevents single position ruin
  2. Asset-level stop-loss discipline
     → Caps max drawdown per position
  3. Portfolio-level volatility targeting
     → Scales down in high-vol regimes
  4. Drawdown management rules
     → Max drawdown threshold → reduce risk
  5. Diversification across uncorrelated factors
     → Factor zoo: not all move together
```

**Volatility-Managed Portfolios** (Moreira & Muir, 2017):
- Scaling equity allocation inversely with realized variance
- Improves Sharpe ratio of equity, momentum, and value strategies
- Papers: 200 (volatility/risk topic)

---

### Layer 5 — Behavioral Factors

**20% Biases → 80% of Retail Investor Underperformance**

| Bias | Description | Impact |
|------|-------------|--------|
| **Overconfidence** | Overestimate skill, underestimate risk | -2% to -5% annually |
| **Loss aversion** | Losses 2× more painful than gains | Selling winners early, holding losers |
| **Recency bias** | Over-weight recent events | Buy high, sell low cycles |
| **Disposition effect** | Sell winners, hold losers | Tax-inefficient, performance drag |
| **Home bias** | Over-concentration in domestic stocks | Poor diversification |

**DALBAR Study**: Average equity fund investor earned ~3.9% annually vs. S&P 500's ~10.3% (2003–2023), primarily due to behavioral timing errors.

---

### Layer 6 — Quantitative / Systematic Approaches

**20% Core Models → 80% of Systematic Alpha**

| Approach | Edge Source | Time Horizon |
|----------|-------------|-------------|
| **Trend following / CTA** | Momentum persistence | 1–12 months |
| **Statistical arbitrage** | Mean reversion, correlation | Days–weeks |
| **Factor investing** | Risk premia harvesting | 1–5 years |
| **ML-based prediction** | Non-linear patterns | Short-medium |
| **Options/volatility strategies** | VRP (variance risk premium) | Monthly |

---

## 3-Year Investment Cycle Breakdown

### C01 — Accumulation Stage (Early Bull Market)

**Characteristics**: Post-crisis/bear market bottom, low valuations, high pessimism, institutional accumulation

**80/20 Strategy**:
1. **Deep value + quality screen** — buy cheap, high-ROE companies when nobody wants them
2. **Broad market index exposure** — beta > 1 pays off in the first recovery leg
3. **Credit recovery signal** — high-yield spread narrowing confirms macro turn

**Key academic support**: Equity risk premium (ERP) at historical highs → Subsequent 5-year returns strongly positive (Damodaran research series)

---

### C02 — Expansion Stage (Mid Bull Market)

**Characteristics**: GDP growth, earnings expansion, rising rates (early), momentum dominates

**80/20 Strategy**:
1. **Momentum + quality** — ride the trend, filter for profitability
2. **Sector rotation** — Technology, Industrials, Materials lead
3. **Factor exposure** — Profitability (RMW) and Investment (CMA) factors active

---

### C03 — Distribution Stage (Late Bull Market)

**Characteristics**: Peak valuations, slowing growth, yield curve flattening/inverting, sentiment extreme

**80/20 Strategy**:
1. **Reduce beta, raise quality** — tilt to defensive sectors
2. **Monitor yield curve** — inversion is the most reliable recession signal
3. **Hedge volatility** — VIX options or CBOE strategies for downside protection

---

### C04 — Contraction Stage (Bear Market)

**Characteristics**: EPS deterioration, rate hikes peak, volatility >25, drawdowns >20%

**80/20 Strategy**:
1. **Risk-off: raise cash or hedge** — volatility scaling
2. **Short-term trading strategies** — high volatility creates short-term momentum
3. **Watch for credit spread widening** — leading indicator of deeper recession

**Research support**: Short-term trading anomalies amplify during high-volatility regimes (papers: 200 short-term trading, 200 volatility)

---

### C05 — Recovery Stage (Early Cycle Turn)

**Characteristics**: Policy pivot (rate cuts), beaten-down valuations, early momentum turn

**80/20 Strategy**:
1. **Rate-sensitive sectors** — Financials, Real Estate benefit from rate cuts
2. **Small-cap tilt** — historically outperform at cycle turns
3. **Return predictability window** — 12-month forward ERP is highest here

---

## Paper Distribution by Topic

| File | Topic | Papers | Cycle | Key Views / Conclusions / Recommended Practices |
|------|-------|--------|-------|------------------------------------------------|
| 01-momentum.json | Price momentum | 2 | C02 | Momentum effect exists but is **universe-dependent** — not homogeneous across market caps or sub-indices. Can be quantified with physics-inspired metrics (velocity × mass). Recommend filtering by liquidity before applying momentum screens. |
| 02-technical-analysis.json | Technical analysis | 23 | All | TA can be **mathematically justified** as an optimization problem (moving averages maximize log-utility under certain dynamics). Reconcilable with semi-strong EMH. Price velocity + acceleration are more robust signals than lagging indicators. Support/resistance levels modeled as optimal stopping boundaries. Recommend: use TA for timing only, not selection. |
| 03-short-term-trading.json | Short-term trading strategies | 200 | C04, C02 | Price impact of trades is **universal** across asset classes. LSTM/deep learning models outperform classical methods for high-frequency patterns. Social media sentiment (Twitter/Reddit) predicts short-term reversals. Trading halts in high-vol regimes create bid-ask spread anomalies exploitable intraday. Recommend: combine LSTM with sentiment signals; avoid market-impact blindness. |
| 04-earnings.json | Earnings announcements | 7 | C02, C03 | **Post-Earnings Announcement Drift (PEAD)** persists — prices continue to drift for weeks post-announcement. Retail investor reaction depends on holding horizon. Text features in press releases (LLM-embedded narratives) predict same-day returns. Options implied vol spikes before EA and collapses after. Recommend: trade PEAD with 3–5 day horizon; use LLM-parsed text for surprise direction. |
| 05-fundamental-value.json | Fundamental/value investing | 20 | C01 | ML multi-factor models (436+ features) outperform single-ratio screening. Analyst report text contains alpha when embedded with LLMs. **Systematic value investing framed as optimization** beats ad-hoc screening. VaR-constrained mean-variance portfolios shift allocation conservatively. Recommend: combine quantitative scoring with qualitative LLM-parsed filings. |
| 06-business-cycle.json | Business cycle indicators | 46 | All | Business cycles are **endogenously driven** by coupled stock-market and real-economy dynamics, not purely exogenous shocks. Oil price and interest rate shocks are primary triggers. Cycles synchronize internationally. Recommend: use LEI composite (orders, hours, claims, stocks) as single best-of-class cycle indicator; phase identification precedes sector allocation. |
| 07-sector-rotation.json | Sector rotation | 4 | C02 | Factor models + fundamental screens (CPI, GDP stage) together outperform either alone. ML ensemble methods dynamically weight models based on recent accuracy. RL agents show promise for real-time rotation decisions. Recommend: two-stage process — macro regime identification → sector scoring → position sizing. Do NOT rotate based on single macro signal. |
| 08-factor-investing.json | Multi-factor strategies | 21 | All | Deep multi-factor models capture **nonlinear interactions** missed by linear Fama-French. Regime-switching jumps must be modeled; ignoring them understates tail risk. **LLMs alone cannot reliably generate stock predictions** — human/quantitative oversight still required. Recommend: use 4–5 factor exposure + regime awareness; avoid factor crowding. |
| 09-market-regime.json | Market regime detection | 42 | All | Regimes (bull/bear/stress) are **statistically distinct** — strategy parameters must adapt per regime. Path signatures (Wasserstein distance clustering) outperform rolling-window HMM for detection speed. Bear/bull transitions driven by asymmetric causality between financial and real sectors. Recommend: fit separate strategy parameters per regime; use unsupervised clustering for objective regime labeling. |
| 10-equity-premium.json | Equity risk premium | 143 | C01, C05 | ERP is most reliably estimated from **options market term structure** (model-light SPX chains). ERP varies dramatically with macro conditions; COVID-19 created historically extreme readings. Size premium is alive when controlling for liquidity (dollar-turnover basis). Recommend: monitor real-time ERP from options for entry/exit timing; high ERP (>5%) is the strongest long-term buy signal. |
| 11-portfolio.json | Portfolio optimization | 151 | All | **Imperfect/missing data makes standard MVO dangerous** — leads to concentrated, fragile portfolios. Hybrid regime + BL + elastic-net regularization produces most robust multi-asset allocations. Active vs. passive can be unified as a tracking/outperformance trade-off problem. Recommend: use risk parity or regularized BL over raw MVO; rebalance on threshold drift (5%), not calendar. |
| 12-volatility.json | Volatility modeling | 200 | C04 | **HAR model** (heterogeneous autoregressive) is the benchmark — captures long-memory, asymmetry, and intraday patterns. Network models (graph signal processing across stocks) significantly improve S&P 500 vol forecasts. Macro attention + sentiment predict future volatility beyond price-based models. Leverage effect (negative return → higher vol) is universal. Recommend: use HAR-RV as baseline; layer in macro sentiment for medium-horizon vol targeting. |
| 13-interest-rate.json | Interest rates & monetary policy | 199 | C03, C05 | Fed policy has **long-range dependence** effects on rates — changes persist structurally. FOMC surprises (information effects beyond rate decision) are the primary spillover channel to global markets. Monetary policy uncertainty independently impacts crypto and risk assets. Recommend: decompose Fed actions into "pure rate" vs. "information/signal" components; the latter drives most cross-asset volatility. |
| 14-inflation.json | Inflation & investing | 127 | C03 | **Bitcoin does NOT hedge inflation** (paper confirms negative correlation with inflation news). Inflation is increasingly driven by international conditions, not just domestic demand. Financial shocks transmit via firm balance sheets (debt-inflation channel). Public attention threshold creates nonlinear inflation dynamics — expectations matter. Recommend: use energy/commodities and TIPS for inflation hedging; avoid crypto as an inflation hedge. |
| 15-prediction.json | Market prediction models | 131 | All | Stock markets have **multifractal, time-varying predictability** — not purely random walk. Agentic LLMs (real-time web access) show early evidence of nowcasting ability. Predictability alone doesn't guarantee profit — transaction costs and capacity constraints erode edge. Deep learning (LSTM, Transformers) outperform classical stat models but overfit easily. Recommend: ensemble ML with strict OOS validation; treat predictability as a decaying signal requiring continuous refresh. |
| 23-risk-management.json | Risk management | 2 | C04 | **Meta Portfolio Method** (adaptive ML strategy selection) outperforms fixed-weight strategies by selecting regime-appropriate sub-strategies. Fractal/long-memory model of risk better captures realistic correlation structure than standard MPT. Recommend: use adaptive strategy switching based on realized regime; do not use static correlation matrices for risk parity. |
| 13-interest-rate.json | Interest rates & monetary policy | 199 | C03, C05 |
| 14-inflation.json | Inflation & investing | 127 | C03 |
| 15-prediction.json | Market prediction models | 131 | All cycles |
| 16-long-run-return.json | Long-run return | 0 | C01 |
| 17-demographics.json | Demographic trends | 0 | Long-term |
| 23-risk-management.json | Risk management | 2 | C04 |

---

[Chinese README](README.zh-CN.md) | [Knowledge Document](us-stock-market.md) | [Back to Main](../README.md)
