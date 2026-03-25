# arxiv.qbio-health — 0~80岁全年龄段人类健康关键因素研究

**1,125 篇 arXiv 摘要**，来自 `q-bio`（定量生物学）类别的 7 个主题搜索，覆盖各年龄段人类健康最有证据支持的核心因素。

**核心目标（帕累托 80/20 法则）：** 找出约 20% 的关键因素，决定约 80% 的健康结果 —— 为普通人提供参考。

## 搜索主题

| # | 主题 | 关键词 | 论文数 | 结果文件 |
|---|------|--------|--------|----------|
| 01 | 衰老与长寿 | aging / longevity / lifespan | 200 | [01-longevity.json](search-results/01-longevity.json) |
| 02 | 饮食与代谢 | diet / nutrition / fasting / metabolism | 200 | [02-diet.json](search-results/02-diet.json) |
| 03 | 运动与体能 | exercise / fitness / muscle | 200 | [03-exercise.json](search-results/03-exercise.json) |
| 04 | 睡眠与昼夜节律 | sleep / circadian | 186 | [04-sleep.json](search-results/04-sleep.json) |
| 05 | 肠道菌群 | microbiome / gut / probiotic | 110 | [05-microbiome.json](search-results/05-microbiome.json) |
| 06 | 死亡率与风险因素 | mortality / survival / death | 200 | [06-mortality.json](search-results/06-mortality.json) |
| 07 | 补剂与干预 | supplement / intervention / drug | 114 | [07-supplement.json](search-results/07-supplement.json) |

**原始结果 1,210 篇 → 去重后 1,184 篇 → 相关性过滤后 1,125 篇**

## 摘要文件

- [`abstracts/`](abstracts/) — 1,125 个 `.txt` 文件，每篇包含标题、作者、arXiv ID、URL 和摘要
- [`abstracts_removed/`](abstracts_removed/) — 67 篇已过滤（非人类模型生物、物理/数学、非健康生物学）

## 搜索参数

- 类别：`q-bio`（定量生物学全子类别）
- 排序：`relevance`（相关度优先）
- 搜索字段：`-t` 标题搜索 + OR 语法（如 `"aging or longevity or lifespan"`）
- 工具：[arxs](https://github.com/host452b/arxs) v1.0.3

## 相关性过滤说明

按人类健康关键词打分（人类受试者、临床、饮食、运动、睡眠、肠道菌群、死亡率、生物标志物等），扣分项包括：非人类模型生物（秀丽隐杆线虫、酵母、大肠杆菌）、物理内容、非健康生物学。得分为负的论文移至 `abstracts_removed/`。

---

[English README](README.md) | [返回主目录](../README.md)
