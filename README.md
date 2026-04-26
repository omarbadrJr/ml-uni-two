# MAGIC Gamma Telescope Classification - Assignment 2

This project contains a simple, step-by-step notebook implementation for the assignment requirements using the MAGIC dataset.

## Files

- `src\assignment2_classification.ipynb` - main notebook
- `data\raw\magic04.data` - raw dataset input
- `data\processed\processed_balanced.csv` - balanced dataset
- `data\processed\train.csv` - training split (70%)
- `data\processed\test.csv` - testing split (30%)

## Requirements

- Python 3.10 or newer
- pandas
- matplotlib
- scikit-learn
- jupyter

Install:

```bash
pip install pandas matplotlib scikit-learn jupyter
```

## Run

1. Put the raw file in `data\raw\magic04.data`.
2. Open `src\assignment2_classification.ipynb`.
3. Run all cells in order.

## Notebook workflow

1. Load the raw dataset with explicit column names.
2. Balance classes by downsampling `g` to match `h`.
3. Split data into stratified train/test (70/30).
4. Tune `n_estimators` for AdaBoost and Random Forest using cross-validation.
5. Train and evaluate:
   - Decision Tree
   - Naive Bayes
   - AdaBoost
   - Random Forest
6. Report accuracy, precision, recall, F1-score, and confusion matrix for each model.

## Output

After running the notebook, processed CSV files are saved to `data\processed\`.
