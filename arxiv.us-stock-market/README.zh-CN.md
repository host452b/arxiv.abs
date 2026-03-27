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

| 旧范式 | 触发事件 | 新范式 |
|---|---|---|
| **CAPM single-factor model** — beta explains all returns | Fama-French (1992): size and value anomalies | **Multi-factor risk models** — 5-factor + momentum premia |
| **Efficient Market Hypothesis** — prices fully reflect all information | Shiller / behavioral finance: excess volatility puzzle | **Factor premia + behavioral biases** — PEAD, momentum, and value persist |
| **Constant volatility (Black-Scholes)** — σ is a fixed parameter | GARCH / stochastic vol models (1986+): Engle, Heston | **Regime-switching volatility** — vol clusters and mean-reverts over time |
| **Fundamental analysis only** — DCF, P/E, analyst calls | Quant revolution (1980s–): Simons, Asness, Fama | **Systematic / factor investing** — risk premia harvested with discipline |

**已被推翻的认知误区:**
- ✗ "技术分析是金融占星术" → 移动平均策略在特定机制下有正期望值
- ✗ "比特币是对冲通胀工具" → 比特币与通胀冲击呈负相关；它是风险资产
- ✗ "均值方差优化可靠地产生最优投资组合" → 贝叶斯/鲁棒方法更优

