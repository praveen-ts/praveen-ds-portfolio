# Credit Risk Scorecard

## Problem
Built an interpretable credit risk scorecard to predict loan default risk, benchmarked against a black-box ensemble model.

## Data
UCI German Credit dataset (real, publicly available) — 1,000 loan applicants with 20 features (financial history, employment, demographics).

## Approach
- Weight of Evidence (WOE) transformation + Information Value (IV) for feature selection
- Logistic regression scorecard (fully interpretable, industry-standard for credit risk)
- Benchmarked against XGBoost as a black-box challenger model

## Key Results
- **AUC: 0.823** | **Gini: 0.647**
- WOE/IV logistic regression scorecard outperformed XGBoost on this dataset — a notable finding, since tree-based ensembles are often assumed to beat simpler models by default
- Fully interpretable: each score component traces back to a specific applicant attribute, which matters for regulated lending decisions

## Limitations (disclosed)
- No reject inference applied (dataset only contains approved-and-observed loans, a common industry constraint)
- Pilot-scale dataset (1,000 records) — production deployment would need a larger, more diverse sample
- Static point-in-time scorecard, not adjusted for economic cycle drift

## Why this approach
Interpretability isn't just a nice-to-have in credit risk — it's often a regulatory requirement. This project demonstrates that a well-engineered interpretable model can match or beat ensemble methods, avoiding the interpretability-performance tradeoff often assumed to be unavoidable.
