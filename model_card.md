# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:** 
The model takes as input a set of features derived from the Home Credit Default Risk dataset, including customer demographic information, credit history, and loan application details. Important features include:

EXT_SOURCE_1, EXT_SOURCE_2, EXT_SOURCE_3 (external credit scores)

DAYS_BIRTH, DAYS_EMPLOYED

Credit balances, overdue days, annuity income ratio, etc.

**Output:** 
A binary prediction indicating whether a customer is likely to default on a loan (TARGET = 1) or not (TARGET = 0).

**Model Architecture:** 
The model is based on the LightGBM gradient boosting decision tree algorithm. Feature selection and preprocessing were performed, and model training was done using stratified K-fold cross-validation. The final model was selected based on its average AUC across folds.

## Performance

Evaluation Metric: Area Under the Curve (AUC)

Cross-validation AUC (average over folds): Approximately 0.754

Feature Importance: Top contributing features included EXT_SOURCE_2, EXT_SOURCE_3, DAYS_BIRTH, and credit-related ratios.

## Limitations

The dataset may contain historical or reporting biases which could affect model fairness.

The model performance may degrade on populations different from the training dataset (e.g., other countries, time periods, or financial institutions).

Missing data and imputation may introduce noise.

Some highly predictive features (e.g., DAYS_EMPLOYED) might encode leakage or spurious correlations.

## Trade-offs

Accuracy vs Interpretability: LightGBM offers strong predictive power but can be less interpretable than simpler models. SHAP values help mitigate this.

Overfitting Risk: Complex feature engineering and tree models can overfit if cross-validation is not properly applied.

Feature Leakage: Some features may inadvertently reveal future information if not carefully validated (e.g., overlapping time windows).
