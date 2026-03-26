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

| File | Topic | Papers | Cycle Relevance |
|------|-------|--------|----------------|
| 01-momentum.json | Price momentum | 2 | C02 |
| 02-technical-analysis.json | Technical analysis | 23 | All cycles |
| 03-short-term-trading.json | Short-term trading strategies | 200 | C04, C02 |
| 04-earnings.json | Earnings announcements | 7 | C02, C03 |
| 05-fundamental-value.json | Fundamental/value investing | 20 | C01 |
| 06-business-cycle.json | Business cycle indicators | 46 | All cycles |
| 07-sector-rotation.json | Sector rotation | 4 | C02 |
| 08-factor-investing.json | Multi-factor strategies | 21 | All cycles |
| 09-market-regime.json | Market regime detection | 42 | All cycles |
| 10-equity-premium.json | Equity risk premium | 143 | C01, C05 |
| 11-portfolio.json | Portfolio optimization | 151 | All cycles |
| 12-volatility.json | Volatility modeling | 200 | C04 |
| 13-interest-rate.json | Interest rates & monetary policy | 199 | C03, C05 |
| 14-inflation.json | Inflation & investing | 127 | C03 |
| 15-prediction.json | Market prediction models | 131 | All cycles |
| 16-long-run-return.json | Long-run return | 0 | C01 |
| 17-demographics.json | Demographic trends | 0 | Long-term |
| 23-risk-management.json | Risk management | 2 | C04 |

---

[Chinese README](README.zh-CN.md) | [Knowledge Document](us-stock-market.md) | [Back to Main](../README.md)
