# Healthcare Patient Readmission Prediction

## Problem
Predicted 30-day hospital readmission risk to support early intervention planning, walking through a deliberate simple-to-complex modeling progression rather than jumping straight to the most complex model available.

## Data
UCI Diabetes Readmission dataset (real, public) — patient encounter records with diagnosis codes, lab procedures, and readmission outcomes.

## Approach
- EDA with missingness, outlier, and class-imbalance analysis (real readmission rate ~11%, more imbalanced than typical simulated assumptions)
- Model progression: Logistic Regression → Decision Tree → Random Forest → XGBoost, with cross-validated ROC-AUC compared at each step
- Threshold tuning for precision/recall/F1 tradeoffs relevant to a clinical use case
- Unsupervised patient clustering (K-Means) validated against ground-truth readmission via UMAP visualization
- SHAP for model interpretability (beeswarm + individual patient waterfall)
- Hyperparameter tuning via Optuna, experiment tracking via MLflow
- Prophet time-series forecasting for admission volume trends

## Key Results
- Full model comparison across 4 algorithms, with an explicit "read this as a story, not a leaderboard" interpretation — flat/declining scores with added complexity is treated as a valid finding about the underlying relationship, not a failure
- SHAP-based explainability for both global feature importance and individual patient-level predictions

## Limitations (disclosed)
- ICD-9 diagnosis codes bucketed into broad categories (Diabetes, Circulatory, Respiratory, etc.) rather than using granular codes, trading precision for interpretability
- Time-series admission data is simulated (clearly labeled), used to demonstrate Prophet forecasting methodology rather than real hospital volume

## Why this approach
Healthcare prediction tasks often over-index on model complexity. This project deliberately documents the reasoning at each step-up in complexity, since a defensible "why" matters more than reaching for the most sophisticated technique available.
