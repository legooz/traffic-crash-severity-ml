# Data preparation

Sources: [NHTSA CRSS](https://www.nhtsa.gov/crash-data-systems/crash-report-sampling-system) and [NHTSA FARS](https://www.nhtsa.gov/research-data/fatality-analysis-reporting-system-fars).

Obtain annual tables and coding manuals from NHTSA. Historical notebooks use 2023 material and prepared subsets. A similarly named CSV does not by itself reproduce the research cohort.

Keep the raw tables separate: put CRSS files in `data/CRSS2023CSV/` and FARS files in `data/FARS2023NationalCSV/` (or those subdirectories under `PROJECT_DATA_DIR`). Both archives contain names such as `accident.csv`; do not combine them into one directory. Prepared merged/subset CSVs belong directly under the configured data directory.

Organized model notebooks expect these files in `data/`, or `PROJECT_DATA_DIR`:

- `AI_UNITE_CRSS_FARS_merged_IMPAIRMENT_ONLY.csv`
- `AI_UNITE_CRSS_FARS_merged_subset_DRIMPAIR_ONLY.csv`
- `AI_UNITE_CRSS_FARS_merged_subset_same_features.csv`

Read the chosen notebook for its input. The cleaning notebook contains historical intermediate filenames and joins to review against annual codebooks. It is not the final CARE preprocessing pipeline. Existing legacy CSVs are historical inputs, not a documented cohort definition. New local exports and model artifacts are ignored by Git.
