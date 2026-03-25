# arxiv.qbio-health — Key Health Factors Across the Human Lifespan (0–80)

**1,125 arXiv abstracts** from 7 targeted searches in the `q-bio` category, covering the most evidence-backed factors for human health across all life stages.

**Core principle (Pareto 80/20):** Identify the ~20% of key factors that drive ~80% of health outcomes — for practical reference by ordinary people.

## Search Topics

| # | Topic | Keywords | Papers | Results File |
|---|-------|----------|--------|--------------|
| 01 | Aging & Longevity | aging / longevity / lifespan | 200 | [01-longevity.json](search-results/01-longevity.json) |
| 02 | Diet & Metabolism | diet / nutrition / fasting / metabolism | 200 | [02-diet.json](search-results/02-diet.json) |
| 03 | Exercise & Fitness | exercise / fitness / muscle | 200 | [03-exercise.json](search-results/03-exercise.json) |
| 04 | Sleep & Circadian | sleep / circadian | 186 | [04-sleep.json](search-results/04-sleep.json) |
| 05 | Gut Microbiome | microbiome / gut / probiotic | 110 | [05-microbiome.json](search-results/05-microbiome.json) |
| 06 | Mortality & Risk Factors | mortality / survival / death | 200 | [06-mortality.json](search-results/06-mortality.json) |
| 07 | Supplements & Interventions | supplement / intervention / drug | 114 | [07-supplement.json](search-results/07-supplement.json) |

**1,210 raw results → 1,184 deduplicated → 1,125 after relevance filtering**

## Abstracts

- [`abstracts/`](abstracts/) — 1,125 `.txt` files, each containing title, authors, arXiv ID, URL, and abstract
- [`abstracts_removed/`](abstracts_removed/) — 67 filtered-out papers (non-human models, physics, non-health biology)

## Search Parameters

- Category: `q-bio` (all sub-categories)
- Sort: `relevance`
- Search field: `-t` title search with OR syntax (e.g. `"aging or longevity or lifespan"`)
- Tool: [arxs](https://github.com/host452b/arxs) v1.0.3

## Relevance Filtering

Papers scored by presence of human-health keywords (human subjects, clinical, diet, exercise, sleep, microbiome, mortality, biomarkers, etc.) and penalized for non-human model organisms (C. elegans, yeast, E. coli), physics content, or non-health biology. Papers with negative scores moved to `abstracts_removed/`.

---

[中文说明](README.zh-CN.md) | [Back to main](../README.md)
