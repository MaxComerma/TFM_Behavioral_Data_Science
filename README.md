# Network Analysis of Depression and Anxiety Symptoms

**MSc in Behavioral Data Science (IL3–UB) · Final Project · MetrikaMind**

Exploratory network analysis of relationships between depression and anxiety symptoms in a quota-representative sample of the Spanish population. The project combines data preparation, zero-order Spearman correlation networks, centrality analysis and community detection.

> **Portfolio note:** source documentation and the original academic report are primarily in Spanish.

## At a glance

| | |
|---|---|
| **Team** | Max Comerma · Pietro Olivetti · María Barraza |
| **Supervision** | David Gallardo (UB) |
| **Methods** | Data preparation · zero-order Spearman correlation networks · centrality · community detection |
| **Main tools** | R · R Markdown · qgraph · igraph · bootnet · psych · tidyverse |
| **Data** | Original participant-level dataset is not included in this public repository |

## Key findings

- In the PHQ-9 network, the most central symptoms by strength were item 1 (anhedonia), item 2 (depressed mood / hopelessness) and item 6 (feelings of failure).
- In the full depression/anxiety network, PROMIS depressed-mood items showed high centrality in the reported analysis.
- The BFI-2 item “full of energy” showed high betweenness in the reported network; this should be treated as a hypothesis about connectivity, not as evidence of causal influence.

Exact numerical values for selected centrality results are intentionally not reproduced here until they are verified against the final exported result tables.

## Methodological notes

The **primary network analysis is based on zero-order Spearman correlations**. A separate EBICglasso/bootnet workflow exists in the research material and should not be interpreted as regularization or stability validation of the primary zero-order network unless explicitly reported for that network.

Because the data are cross-sectional, network edges describe statistical associations and do not establish causal direction or temporal order. Centrality represents mathematical prominence within a network, not clinical or causal importance.

PROMIS contains more items than several of the other instruments. Its apparent prominence may therefore partly reflect measurement structure, item redundancy or scale size. This should be investigated before making substantive interpretations.

## Repository structure

```text
TFM_Behavioral_Data_Science/
├── README.md
├── .gitignore
├── R/
│   ├── 01_data_cleaning.Rmd
│   └── 02_network_analysis.Rmd
├── data/
│   └── README.md
├── figures/
├── results/
│   └── README.md
├── references/
└── report/
    └── TFM
```

The repository keeps the main analysis workflow under `R/`. Temporary drafts and participant-level source data have been removed from the public working tree.

## Reproduction

The analysis requires R and the packages used in the R Markdown files, including:

```r
install.packages(c(
  "dplyr", "igraph", "qgraph", "bootnet", "corpcor",
  "openxlsx", "ggplot2", "tidyr", "matrixcalc",
  "e1071", "networktools", "EGAnet"
))
```

Workflow:

1. Provide an approved dataset following the expected variable structure.
2. Run `R/01_data_cleaning.Rmd`.
3. Run `R/02_network_analysis.Rmd`.
4. Review exported figures and result tables before drawing substantive conclusions.

The current repository does not include an `renv.lock`, so exact package-version reproducibility is not yet guaranteed.

## Data and privacy

The original TFM dataset contained participant-level psychological and sociodemographic variables. It has been removed from this public repository. Do not publish or redistribute the original data without confirming the applicable consent, anonymisation and data-governance requirements.

## Limitations and next steps

- The primary network is based on zero-order correlations rather than a regularized/stability-selected network.
- Cross-sectional data do not support causal or temporal interpretations.
- Centrality estimates should be interpreted as network statistics, not clinical intervention targets.
- PROMIS item-count and redundancy effects should be assessed.
- The original project contains exploratory and supplementary analyses that require clearer separation from the primary workflow.
- A synthetic or approved de-identified dataset plus a pinned R environment would improve portfolio reproducibility.

## Team

**Max Comerma · Pietro Olivetti · María Barraza**

Supervised by **David Gallardo (UB)** and developed in collaboration with **MetrikaMind**.
