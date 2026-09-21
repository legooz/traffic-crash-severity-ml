# Traffic Crash Severity: Models and Explanations

Python research notebooks for preparing CRSS/FARS crash records, comparing severity classifiers, and inspecting model behavior with SHAP.

**Status:** research notebook collection. The organized notebooks accompany the original traffic-analysis files. They have been cleaned for sharing, but the complete data-processing and training sequence has not been rerun in a fresh environment.

## Related publication: CARE

**[CARE: Counterfactual Attention for Fatality Risk Estimation in Drivers with Non-Substance Impairments](https://ieeexplore.ieee.org/document/11623862)**

Lars Goozen, Masoumeh Heidari Kapourchali, and Kenrick Mock.

*2026 IEEE Intelligent Vehicles Symposium (IV)*, pp. 2046–2052.

DOI: [10.1109/IV66570.2026.11623862](https://doi.org/10.1109/IV66570.2026.11623862).

The paper studies fatality-risk estimation for drivers with non-substance impairments and counterfactual explanations of model predictions. This repository contains related data-preparation, baseline-classification, and SHAP experiments; **it is not the complete CARE implementation or a reproduction of the paper's results**. Cite the paper for the CARE method and reported findings; see [CITATION.cff](CITATION.cff) for citation metadata.

Read the paper through IEEE Xplore. A publisher PDF is not redistributed here.

## What is included

| Notebook in `notebooks/` | Purpose |
|---|---|
| `AI-UNITE-Traffic-dataset-cleaning.ipynb` | Prepare accident, person, vehicle, and impairment records. |
| `RandomForest_CrashAnalysisProject.ipynb` | Random Forest baseline and explanation experiments. |
| `DecisionTree_CrashAnalysisProject.ipynb` | Decision-tree classification. |
| `MultinominalLR_CrashAnalysisProject.ipynb` | Multinomial logistic regression. |
| `XGBoost_CrashAnalysisProject.ipynb` | Gradient-boosted classification experiments. |
| `LightGBM_CrashAnalysisProject.ipynb` | LightGBM classification. |
| `CatBoost_CrashAnalysisProject.ipynb` | CatBoost classification and SHAP explanations. |
| `CatBoost_SHAP_Analysis.ipynb` | Separate CatBoost/SHAP experiment. |

The original root notebook and `map/` / `finetuning/` material remain as earlier experiments. These are related baselines, **not the final CARE implementation**.

## Repository scope: why some work is not included

This repository is a curated snapshot of the traffic-research files currently available for this archive, not a complete record of the project. The broader research includes work described in the publication that is not represented by the uploaded notebooks. Repository contents should not be used as a complete measure of the research contributions.

| Material | Current availability |
|---|---|
| CRSS/FARS preparation and conventional classifier/SHAP experiments | Included in the organized notebooks, alongside earlier exploratory files. |
| Final CARE-specific model, adaptation, and counterfactual-generation implementation | Not included. The final implementation has not yet been located among the local research files reviewed for this archive. |
| Exact preprocessing, final cohort/split definitions, configurations, and evaluation scripts supporting the paper | A complete, verified reproduction package is not included. Historical notebook settings and legacy CSVs are not substitutes for that package. |
| Final trained weights/checkpoints and experiment artifacts | Not included as a validated CARE release. |
| Data | Some legacy CSVs remain from earlier commits, but the complete raw/prepared research data and a verified final cohort are not bundled. See [DATA.md](DATA.md). |
| Notebook output and execution state | Cleared in the organized sharing copies; the repository is not a preserved results log. |
| Publisher PDF, acceptance correspondence, and private research records | Not redistributed here; use the paper link for the publication. |

Some material was deliberately excluded from the sharing copies, while other material—especially the final CARE implementation—has not been recovered for this archive. Additional source or artifacts should be added only after their provenance, relationship to the paper, and sharing permissions are verified.

For the remaining release requirements, see the [CARE reproducibility checklist](REPRODUCIBILITY.md). Until those materials are available, treat the paper as the source for published methods/results and this repository as the available related code, without claiming the two are identical.

## Setup

Use Python 3.11 or 3.12 in a separate environment:

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
python -m jupyter lab
```

Start with data preparation, then select a model notebook. The organized notebooks use `data/` by default; set `PROJECT_DATA_DIR` before starting Jupyter to use another directory.

## Data and evaluation

See [DATA.md](DATA.md) for sources and filenames. The classifiers use different prepared subsets; their scores are not automatically comparable without matching cohorts, preprocessing, and splits. Inspect feature leakage, imbalance, and sampling assumptions before interpreting results. SHAP describes model behavior, not established causal effects.

Saved outputs have been cleared. CI checks notebook structure and Python syntax, not predictive accuracy. Dependency files are starting environments, not recovered historical lockfiles.

## Attribution

Research code maintained by Lars Goozen. The CARE publication is coauthored with Masoumeh Heidari Kapourchali and Kenrick Mock; paper authorship does not establish authorship of every archived file. See [NOTICE.md](NOTICE.md) for attribution and licensing status. Research/code-sharing rights should be confirmed before changing repository visibility.
