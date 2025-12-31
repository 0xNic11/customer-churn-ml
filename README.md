# Customer Churn Prediction — End-to-End Machine Learning Project

## Overview
This project demonstrates a complete, production-style machine learning workflow for predicting customer churn.
The focus is on **correctness, reproducibility, and decision-quality**, not on flashy or over-engineered techniques.

The notebooks are structured to reflect how a real ML project evolves: from data preparation, to baselines,
to proper preprocessing, to tuning, and finally to a defensible final model.

## Business Problem
Customer churn represents lost revenue and increased acquisition costs.
The objective of this project is to build a classification model that:
- Identifies customers at high risk of churn
- Produces interpretable, interview-defensible results
- Can support downstream retention decisions

## Project Structure
```
.
├── data
│   ├── churn.csv
│   └── churn_preprocessed.csv
├── notebooks
│   ├── churn_day23_preprocessing.ipynb
│   ├── churn_day24_baseline_models.ipynb
│   ├── churn_day25_scaling.ipynb
│   ├── churn_day26_hyperparameter_tuning.ipynb
│   └── churn_final_model.ipynb
├── README.md
└── requirements.txt
```

## Data
- **churn.csv**  
  Raw customer churn dataset used as the single source of truth.

- **churn_preprocessed.csv**  
  Cleaned and encoded dataset generated during preprocessing and used for modeling.
  This file is created in a leakage-safe manner after the train/test split logic is defined.

## Workflow Summary
1. **Preprocessing** (`notebooks/churn_day23_preprocessing.ipynb`)
   - Data inspection and cleaning
   - Encoding categorical features
   - Train/test split performed early to avoid leakage

2. **Baseline Models** (`notebooks/churn_day24_baseline_models.ipynb`)
   - Simple, interpretable models used as performance benchmarks
   - Establishes a reference point before optimization

3. **Scaling & Pipelines** (`notebooks/churn_day25_scaling.ipynb`)
   - Feature scaling applied correctly using train-only fitting
   - Pipelines used to prevent leakage and improve reproducibility

4. **Hyperparameter Tuning** (`notebooks/churn_day26_hyperparameter_tuning.ipynb`)
   - Controlled tuning using cross-validation
   - Search spaces kept intentionally narrow to avoid overfitting

5. **Final Model** (`notebooks/churn_final_model.ipynb`)
   - Final model selection based on validation performance
   - Metrics interpreted in business-relevant terms

## Evaluation Metrics
- Accuracy (reported but not over-emphasized)
- Precision / Recall
- F1-score
- Confusion Matrix

Metrics are interpreted with attention to class imbalance and business cost trade-offs.

## Design Principles
- No data leakage
- Reproducible results (`random_state` used where applicable)
- Minimal complexity
- Clean, readable, review-ready code
- Decisions explained clearly in markdown

## How to Run
1. Create a virtual environment (recommended)
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run notebooks in the order listed above

## Notes for Reviewers
This project is intentionally conservative.
The goal is to demonstrate sound ML judgment and clarity of reasoning rather than advanced modeling tricks.
