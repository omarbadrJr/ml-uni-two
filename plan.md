# Assignment 2 Implementation Plan (MAGIC Data Classification)

## Problem and Current State
The project currently contains the assignment PDF and the raw dataset file; target layout is `data\raw\` for raw input and `data\processed\` for outputs.  
No implementation files exist yet. The assignment requires balanced binary classification, a 70/30 train-test split, model comparison across Decision Tree, AdaBoost, Random Forest, and Naive Bayes, cross-validation tuning for `n_estimators` (AdaBoost and Random Forest), and reporting of accuracy, precision, recall, F-score, and confusion matrix on test data.

## Proposed Approach
Build one reproducible Jupyter notebook as the main deliverable, plus a `README.md` documenting Python version, libraries, setup, and run steps. The notebook will handle the full pipeline end-to-end, reading from `data\raw\` and writing outputs to `data\processed\`.

## Planned Project Structure
- `src\assignment2_classification.ipynb`
- `README.md`
- `data\raw\magic04.data` (raw input)
- `data\processed\processed_balanced.csv` (balanced full dataset)
- `data\processed\train.csv` and `data\processed\test.csv` (post-split datasets)

## Implementation Todos
1. **Environment and project scaffold**
   - Create notebook in `src\` and README skeleton.
   - Define fixed random seed and consistent metric settings for reproducibility.
   - Document required Python version and libraries (`pandas`, `numpy`, `scikit-learn`, `matplotlib`/`seaborn` optional for matrix plots).

2. **Data loading, balancing, and splitting**
   - Load `magic04.data` with explicit column names.
   - Confirm class distribution (`g` vs `h`).
   - Balance classes by randomly downsampling class `g` to match class `h`.
   - Save balanced dataset to `data\processed\processed_balanced.csv`.
   - Split balanced data into 70% train / 30% test with stratification.
   - Save `data\processed\train.csv` and `data\processed\test.csv`.

3. **Model training and cross-validation tuning**
   - Train/evaluate:
     - Decision Tree (no tuning per assignment).
     - Naive Bayes (no tuning per assignment).
     - AdaBoost (tune `n_estimators` via CV on training set).
     - Random Forest (tune `n_estimators` via CV on training set).
   - Use a consistent CV strategy (e.g., stratified k-fold) and select best params from CV score.

4. **Testing-set evaluation and comparison**
   - Evaluate all final models on the held-out test set.
   - Compute: accuracy, precision, recall, F1-score, and confusion matrix.
   - Build a comparison table for all models.
   - Add concise interpretation comments on strengths/weaknesses and tradeoffs.

5. **Submission-quality documentation**
   - Finalize `README.md` with:
     - project goal,
     - data file expectations,
     - Python/library requirements,
     - exact run steps for notebook.
   - Confirm notebook outputs include required metrics and confusion matrices.

## Notes and Decisions
- Use `scikit-learn` implementations as allowed.
- Use train-only CV for tuning to avoid test leakage.
- Keep test set untouched until final evaluation.
- Raw/processed separation is enforced as `data\raw\` and `data\processed\` per your requested submission layout.
