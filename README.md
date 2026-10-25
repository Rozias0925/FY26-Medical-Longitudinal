# Simulation Benchmark

[Read the bilingual research report](https://rozias0925.github.io/FY26-Medical-Longitudinal/)

Mixed-effects machine learning for small-sample longitudinal data, presented in two parts:

- **Part I — Core:** 15 settings and 3,350 simulation replicates, covering feature recovery, prediction, and function recovery.
- **Part I — Direction:** 11 settings and 2,350 validation replicates, covering direction decisions and function recovery.
- **Part II — Eight-model comparison:** Mean, LMM, GAM, RF, GPR, MERF, GAMM, and BART, evaluated for unknown-size factor selection and direction-risk calibration. Paired prediction and curve-recovery experiments compare LMM, GPR, MERF, GAMM, and BART. Numerical sensitivity and stage-specific fit diagnostics are reported separately.

The bilingual report describes the generating conditions, model specifications, calibration and validation procedures, scenario-specific rankings, Monte Carlo uncertainty, and analysis strategy. This simulation study forms part of the author's project in collaboration with National Taiwan University Hospital. All simulation data are synthetic; no patient information was used in these simulations.

This directory serves the static report, local mathematical fonts, and reviewed public data in `data/v1/` and `data/v2/`. Each package's `manifest.json` records provenance and SHA-256 hashes. Part II downloads contain aggregate metrics, event counts, calibration settings, and numerical diagnostics. `data/v1/direction/example_curves_rep1.csv` contains curves from one prespecified illustrative simulation replicate.

KaTeX 0.19.0 is distributed under the MIT license; its license is included in `assets/katex/LICENSE`.

© 2026 文君豪. All Rights Reserved.
