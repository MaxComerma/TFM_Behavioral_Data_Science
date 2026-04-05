# Behavioral Data Science Masters Project: Network Analysis of Symptoms of Depression and Anxiety

## Project Overview

This project explores the network structure of symptoms related to depression and anxiety. Using statistical techniques and network analysis, we aim to explore the intricate relationships between various symptoms and their potential implications for mental health research.

## Project Structure

The project is organized into the following directories and key files:

-   data/
    -   data_cleaned.csv
    -   data.xlsx
    -   data_prep_processing.Rmd
-   network_analysis/
    -   net_exploratory.Rmd
-   draft/
    -   exploratory_analysis.Rmd
-   README.md
-   references/
    -   articles
    -   books

### Directories and Files

-   **data/**

    -   `data_cleaning.Rmd`: This R Markdown file contains the data cleaning procedures, including data import, preprocessing, and transformation steps necessary to prepare the raw data for analysis.
    -   `data.xlsx`: The raw dataset containing data related to scales of personality, depression and anxiety.

-   **network_analysis/**

    -   `net_exploratory.Rmd`: This R Markdown file performs the exploratory network analysis, including the creation of correlation matrices, network visualization, and preliminary findings.

-   **draft/**

    -   `All`: This directory will contain graphical outputs from the network analysis, such as network plots and other visualizations that are currently incomplete and/or are just drafts.

-   **references/**

    -   `articles and books`: A collection of relevant research papers, books and other references used throughout the project.

    ## Getting Started

### Prerequisites

To reproduce the analysis, you need to have the following software installed:

-   R (version 4.0 or higher)
-   RStudio
-   Required R packages: `tidyverse`, `qgraph`, `psych`, `knitr`, `rmarkdown`, `dplyr`, `igraph`, `bootnet`, `openxlsx`, `ggplot2`, `tidyr`, `smacof`

### Installation

Install the required R packages by running the following commands in R:

install.packages(c("tidyverse", "qgraph", "psych", "knitr", "rmarkdown", "dplyr", "igraph", "bootnet", "openxlsx", "ggplot2", "tidyr", "smacof"))

### Running the Analysis

-   Data Cleaning: Open the data/data_cleaning.Rmd file in RStudio and knit the document to preprocess the raw data.

-   Network Analysis: Open the network_analysis/net_exploratory.Rmd file in RStudio to perform the exploratory network analysis.
