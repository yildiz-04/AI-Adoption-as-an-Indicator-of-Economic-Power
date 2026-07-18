# AI Adoption as an Indicator of Economic Power

Statistical analysis of AI adoption across 10 countries (2020–2025), paired with a full project-management report documenting how the study itself was planned, run, and delivered.

## Description

Does a country's adoption of artificial intelligence reflect its economic power and international influence? This project tackles that question from two angles, delivered as two companion reports:

1. **Statistical analysis** — seven hypotheses tested across three research axes (national capabilities → adoption, adoption → economic effects, country/regulation → impact), using correlation, ANOVA, multiple regression, the Gini index, and the Lorenz curve on two merged datasets (10-country AI impact panel + 62-country AI capability index).
2. **Project management** — an Agile-run, client-facing (MOA/MOE) project conducted over 90 working days by a 4-person team, covering planning (Gantt, RACI), tooling, cost estimation, and a reflection on plan-vs-actual execution.

## Key findings

- Of the 7 hypotheses tested, only one held up under scrutiny: **AI adoption is negatively correlated with public trust** (R² = 0.50, p = 0.022) — the more a country uses AI, the less its citizens trust it.
- National AI capability rankings (talent, R&D, infrastructure) **do not predict actual adoption**: the USA ranks #1 in capability but only mid-table in adoption; South Korea and Japan ("Rising stars") adopt AI at rates close to the top-ranked "Power players."
- Sector-level job losses, human-AI collaboration effects, and regulation effects were **not statistically significant** at n=200/n=10 — a result the report treats as informative rather than a failure.
- Income gains from AI are relatively evenly distributed across the 10 countries studied (Gini = 0.06).

## Project management highlights

- **Methodology**: Agile, organized in sprints per phase (prep → build → deliver), with regular MOA (client) checkpoints.
- **Planning**: 90 working days, 4 team members, 360 person-days budget, tracked via MS Project (Gantt chart, RACI matrix).
- **Plan vs. actual**: the "build" phase overran from 58 to 72 days (R learning curve), absorbed by compressing the final phase from 25 to 15 days without slipping the delivery date.
- **Tools**: R/RStudio (analysis), Notion (tracking), MS Project (planning), Word (writing), Outlook/Teams/Skype (communication).

## Repository structure

```
.
├── analysis/
│   └── AI_Adoption_Economic_Power.Rmd        # Full R Markdown analysis (reproducible)
├── data/
│   ├── AI_index_db.csv                       # Global AI Index — 62 countries, capability indicators
│   └── Global_AI_Content_Impact_Dataset.csv  # AI impact panel — 10 countries × sector × year
├── report/
│   ├── statistical-analysis-report.pdf       # Full statistical report (French, 7 hypotheses)
│   └── project-management-report.pdf         # Project conduct report (planning, RACI, costs)
└── README.md
```

## Reproducing the analysis

Requirements: R with `tidyverse` and `pastecs` (see the `packages` chunk in the `.Rmd` for the full list). From the `analysis/` folder:

```r
rmarkdown::render("AI_Adoption_Economic_Power.Rmd")
```

The `.Rmd` loads both datasets via relative paths (`../data/...`), so it runs as-is as long as the repository structure is preserved. Note: PDF rendering references a `header.tex` file not included here — knit to `html_document` for the easiest reproduction, or supply your own header for the PDF output.

## Authors

Chancia ISSA · Lina BICHBICHE · Vincent MAUNIER · Njaka RAKOTOBE
BUT Science des Données, IUT de Paris – Rives de Seine, 2025–2026

## Data sources

- Global AI Content Impact Dataset (Kaggle) — 10 countries, 2020–2025, 200 observations
- Global AI Index (Tortoise Media) — 62 countries, national AI capability indicators

## License

Coursework project, shared for educational and portfolio purposes.
