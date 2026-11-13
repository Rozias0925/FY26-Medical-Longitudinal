# Mixed-Effects Machine Learning for Small-Sample and Sparse Longitudinal Data

This project evaluates statistical and machine-learning methods for identifying relevant predictors, estimating response functions, and predicting outcomes in small, sparsely observed longitudinal datasets. An eight-model simulation benchmark examines nonlinear relationships, correlated predictors, subject-level heterogeneity, and incomplete follow-up. This repository contains the public research report and synthetic benchmark results; simulation and model-fitting source code is not included.

**[Research report (English)](https://rozias0925.github.io/FY26-Medical-Longitudinal/#en-overview)** · [繁體中文](https://rozias0925.github.io/FY26-Medical-Longitudinal/#zh-overview)

## Research questions

- How accurately can models identify the true predictors and recover their response functions when each individual has few observations?
- How does prediction differ between new individuals and individuals with an observed history?
- How reliable are estimated relationship directions under predefined error criteria, and how sensitive are results to numerical optimization?

## Study design

The benchmark uses two synthetic frameworks: **Core**, for predictor identification, function recovery, and prediction; and **Direction**, for evaluating directional decisions and response shapes. Conditions include weak signals, nonlinear effects, highly correlated decoy predictors, random intercepts, missing measurements, dropout, and outcome contamination. Sample-size settings include 25–100 individuals with two or four visits.

The model set comprises a mean-only reference, linear mixed models (LMM), penalized additive models (GAM), random forests (RF), Gaussian process regression (GPR), mixed-effects random forests (MERF), generalized additive mixed models (GAMM), and Bayesian additive regression trees with subject random intercepts (BART).

| Experiment | Evaluation design |
|---|---|
| Predictor selection with an unknown number of true factors | Eight models; 15 settings; 200 independent validation replicates per setting. Selection thresholds are calibrated using separate matched global-null simulations. |
| Direction-risk calibration | Eight procedures; six control settings and an identifiable-scenario mixture for calibration; 200 independent validation replicates in each of 11 settings. |
| Paired prediction and function recovery | LMM, GPR, MERF, GAMM, and BART; four Core and six Direction settings; 50 replicates per setting. |
| Numerical sensitivity | Alternative GPR parameter bounds and restarts, LMM solvers, and MERF iteration limits. |

Preprocessing and model tuning use training data, with cross-validation grouped by individual. The report gives scenario-specific results, Monte Carlo uncertainty, paired comparisons, and fit diagnostics.

## Selected findings

- **Predictor recovery:** across 14 settings with nonzero signals, MERF and RF achieved mean exact-set recovery rates of 66.25% and 65.71%, respectively; BART achieved 60.57%. These averages use 2,800 validation replicates per model.
- **Prediction:** BART had the lowest mean new-individual RMSE in all four paired Core settings. In the most difficult setting, its paired RMSE difference from MERF was −0.0017, with a 95% Monte Carlo interval of [−0.0070, 0.0036].
- **Directional reliability:** under the prespecified risk-calibration criteria, all eight direction procedures abstained in independent validation.

## Public materials

| Location | Contents |
|---|---|
| `index.html` | Bilingual research report: methods, mathematical definitions, scenario descriptions, results, and analysis strategy. |
| [`data/v1/`](data/v1/) | Original Core and Direction specifications and results: 3,350 Core replicates and 2,350 Direction validation replicates. |
| [`data/v2/`](data/v2/) | Eight-model selection and direction-calibration results, paired performance comparisons, and numerical diagnostics. |

Data are provided as CSV and JSON files. Each data package includes a manifest recording provenance and SHA-256 checksums.

## Research context

This simulation study forms part of the author's research project in collaboration with National Taiwan University Hospital. All benchmark data are synthetic; no patient information was used in the simulations.

**Author:** [Chun-Hao Wen (文君豪)](https://rozias0925.github.io/Rozias-Website/)

KaTeX is distributed under the MIT license; see [`assets/katex/LICENSE`](assets/katex/LICENSE).

© 2026 文君豪. All Rights Reserved.
