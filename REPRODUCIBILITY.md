# CARE code-release status

The related notebooks in this repository are not a runnable release of the CARE model. The final CARE-specific implementation has not yet been located among the local files reviewed for this archive. The [paper](https://ieeexplore.ieee.org/document/11623862) is the reference for the method and reported findings; those findings have not been reproduced from this repository.

Before calling a future release a CARE reproduction, recover and verify:

- Final model, adaptation, calibration, and counterfactual-generation code.
- Exact preprocessing, feature definitions, dataset years, cohort criteria, merge keys, and missing-value treatment.
- Train/validation/test partitions, seeds, sampling decisions, and leakage checks.
- Evaluation scripts, baseline configurations, and artifacts corresponding to the paper's results.
- Model/checkpoint provenance, exact dependency versions, and hardware requirements.
- Data-access instructions, coauthor attribution, and permission/license to share each artifact.

Historical classifiers, SHAP plots, legacy CSV filenames, and exploratory fine-tuning examples do not establish equivalence to the published model. A successful notebook syntax check is not an evaluation or training run. Missing source is distinguished from intentionally excluded outputs and private correspondence; no unverified reason is assigned to its absence.
