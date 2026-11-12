# Palmer Penguins - Data Cleaning, Visualization and Statistical Inference - R

A reproducible R workflow showing how to handle a fresh dataset: checked cleaning decisions, the right summary for each variable type, and tests chosen from verified assumptions.

## Overview

- **Dataset:** Palmer Penguins (344 penguins, 3 species, 4 body measurements plus sex and year)
- **Task:** clean and describe the data, visualize species differences, then test them statistically
- **Focus:** assumption checks before every test, with parametric and non-parametric results reported side by side

## Results at a glance

| Question | Test | Result |
|---|---|---|
| Do body measurements differ between species? | ANOVA, Kruskal–Wallis, Tukey post hoc | Yes: Gentoo differ from both other species on every measurement; Adelie and Chinstrap differ only by bill length |
| Are Gentoo males heavier than females? | Welch t-test | Yes, by ~800 g (95% CI 700–910 g, p < 0.001) |
| Is sex balanced across species? | Chi-square test of independence | Yes (p = 0.98) |
| Are flipper length and body mass linked? | Pearson correlation | Strong positive correlation (r = 0.87, 95% CI 0.84–0.89) |
| Are bill length and bill depth linked? | Scatter plots, pooled vs by species | Negative when pooled, positive within each species (Simpson's paradox) |

## Approach

1. **Cleaning:** missing values per variable, the 2 empty rows identified by code and dropped, birds of unknown sex kept, range check on every numeric variable.\
   → *Data wrangling in R: tidyverse pipelines (dplyr, tidyr, purrr)*
2. **Description and visualization:** counts for categorical variables, mean ± SD and median (Q1/Q3) per species for continuous ones; density, scatter and violin plots, including a textbook Simpson's paradox on bill shape.\
   → *ggplot2, patchwork, long/wide reshaping, confounding and Simpson's paradox*
3. **Inference:** Shapiro–Wilk normality check, ANOVA and Kruskal–Wallis side by side, Tukey post hoc, Welch t-test, chi-square, Pearson correlation.\
   → *Assumption checking, omnibus vs post hoc tests, reproducible reporting (Quarto, flextable)*

## Tech stack

R · tidyverse · Quarto · flextable · patchwork · ggbeeswarm · wrappedtools

## Files

- `2. Data_Cleaning_Visualisation_Statistical_Inference.md` — rendered results, viewable on GitHub
- `Data_Cleaning_Visualisation_Statistical_Inference_files/` — tables and graphs used by the .md file
