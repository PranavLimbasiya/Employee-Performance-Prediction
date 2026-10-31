# Employee Performance Category Prediction

A machine learning project that predicts employee performance categories using employee-related data.

## Project Objective

Predict the `Performance_Category` of employees using the available employee information. The target has three classes:

- High Performer
- Average Performer
- Low Performer

The notebook uses `perf_train.csv` to build and validate models, then predicts labels for the unseen records in `perf_test.csv`.

## Dataset Files

Place the following files in the same folder as the notebook:

| File | Purpose |
|---|---|
| `perf_train.csv` | Labelled training data used for exploration, training, validation and tuning |
| `perf_test.csv` | Unseen data for final predictions |
| `sample_submission.csv` | Reference file used to check the required submission format |
| `Pranav_Hackathon.ipynb` | Main Jupyter Notebook containing the complete workflow |

The notebook describes 2,000 training rows and 500 test rows. Confirm that your local CSV files match these details before publishing.

> **Dataset note:** Only upload the CSV files if you have permission to share them publicly. Do not publish confidential, personal, or restricted employee information. If the dataset cannot be shared, omit the CSV files and explain in this README how an authorized user can obtain them.

## Technologies and Libraries

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- scikit-learn

## Workflow

1. Load the training, test and sample-submission datasets.
2. Perform exploratory data analysis (EDA), including target distribution and missing-value checks.
3. Prepare numerical and categorical features.
4. Create additional features:
   - `n_missing`: number of missing fields in each employee record
   - `proj_per_exp`: projects completed per year of experience
   - `sal_per_exp`: monthly salary per year of experience
5. Compare Logistic Regression, Random Forest and HistGradientBoosting using stratified 5-fold cross-validation.
6. Evaluate the selected model on a stratified hold-out validation split.
7. Tune HistGradientBoosting hyperparameters using RandomizedSearchCV.
8. Examine permutation-based feature importance.
9. Train models using the full training data and average predictions across five random seeds.
10. Generate and validate `submission.csv`.

## Model Evaluation

The notebook uses:

- Stratified 5-fold cross-validation with accuracy as the scoring metric.
- A stratified 80/20 train-validation split.
- Accuracy, classification report and confusion matrix.
- Randomized hyperparameter search.
- Permutation importance for feature interpretation.

Actual scores depend on the dataset and execution environment. See the notebook output for the measured results; no fixed accuracy is claimed here.

## Repository Structure

```text
Employee-Performance-Prediction/
├── Pranav_Hackathon.ipynb
├── perf_train.csv                 # include only if sharing is permitted
├── perf_test.csv                  # include only if sharing is permitted
├── sample_submission.csv          # include only if sharing is permitted
├── requirements.txt
├── .gitignore
└── README.md
```

## Limitations

- The model's predictions depend on the quality and representativeness of the supplied dataset.
- Cross-validation and hold-out scores are estimates; the hackathon platform evaluates the final unseen test predictions.
- Feature importance indicates model reliance, not proof that a feature causes employee performance.

## Author

**Pranav Limbasiya**

---
If you use or build on this project, please retain appropriate attribution and follow the dataset provider's usage conditions.
