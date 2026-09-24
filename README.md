# Network Analysis of Depression and Anxiety Symptoms

**MSc in Behavioral Data Science (IL3–UB) · Final Project, in collaboration with MetrikaMind**

Exploratory network analysis of how depression and anxiety symptoms relate to each other, using a quota-representative sample of the Spanish population. The goal is to identify the most central symptoms, which could help make screening and intervention more targeted in workplace mental health.

> Documentation and data are in Spanish. Summary below in English.

## At a glance

| | |
|---|---|
| **Sample** | N = 867, quotas by gender, age and province (representative of Spain) |
| **Instruments** | Depression: PHQ-9, CES-D, PROMIS, QIDS · Depression/anxiety: DASS, HADS · Anxiety: GAD, TMAS, SAS · Personality: BFI-2, HEXACO |
| **Methods** | Data cleaning, weighted symptom networks (correlation-based), centrality analysis (strength, betweenness, closeness) |
| **Tools** | R, R Markdown, qgraph, igraph, bootnet, psych, tidyverse |
| **Team** | Max Comerma, Pietro Olivetti, María Barraza · Supervised by David Gallardo (UB) |
| **My role** | [Hypothesis definition and preliminary network analysis / add anything else you did] |

## Key findings

- **PHQ-9 network:** the most central symptoms by strength were item 1 (anhedonia), item 2 (depressed mood / hopelessness) and item 6 (feelings of failure), consistent with DSM-5 core symptoms.
- **Full network (all scales):** PROMIS items on depressed mood dominated strength and closeness (e.g. "felt emotionally exhausted", "felt that nothing could cheer me up").
- **Bridge nodes:** the BFI-2 item "full of energy" showed the highest betweenness, suggesting energy level as a possible link between symptom clusters (hypothesis, not a confirmed result).

## Business case (estimate)

Study cost estimated at ~€18,300. Assuming an average salary of €1,500 and 75% pay during sick leave (€1,125/month), the cost is recovered by avoiding 16–17 sick leaves, or ~366 psychologist consultations (~€50 each). See the report for assumptions.

## Limitations and next steps

- Networks were built from zero-order correlations; a regularized network (EBICglasso) with bootstrap stability analysis (bootnet) is the natural next step.
- Scales with many items (e.g. PROMIS) may appear central partly because of item count/redundancy; item overlap should be assessed.
- Betweenness is known to be less stable; results should be interpreted with caution.
- Cross-sectional data: connections show association, not causal direction or temporal order.
- The originally planned predictive model and comparison with a faking-detection model are not included in this version.

## Repository structure

```
data/              cleaning script (data_cleaning.Rmd) [+ data, see below]
network_analysis/  net_exploratory.Rmd
references.md      bibliography
report/            final report (PDF, Spanish)
```

## Data

- *The dataset is not included because it belongs to the MetrikaMind/UB study.*

## Reproduce

```r
install.packages(c("tidyverse", "qgraph", "psych", "knitr", "rmarkdown",
                   "igraph", "bootnet", "openxlsx", "smacof"))
```

1. Knit `data/data_cleaning.Rmd` to preprocess the data.
2. Knit `network_analysis/net_exploratory.Rmd` to reproduce the networks and centrality measures.

Requires R ≥ 4.0 and RStudio.

## References

Fried et al. (2016) · Borsboom (2017) · Borsboom et al. (2021) · Forbes et al. (2021) · Deserno et al. (2022) · Cai et al. (2022). Full list in `references.md`.
