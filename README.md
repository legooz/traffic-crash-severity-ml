# Traffic Crash Severity: Models and Explanations

Python research notebooks for preparing CRSS/FARS crash records, comparing severity classifiers, and inspecting model behavior with SHAP.

**Status:** research notebook collection. The organized notebooks accompany the original traffic-analysis files. They have been cleaned for sharing, but the complete data-processing and training sequence has not been rerun in a fresh environment.

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

Research work maintained by Lars Goozen. Related publication: [CARE](https://ieeexplore.ieee.org/document/11623862). See [NOTICE.md](NOTICE.md).
