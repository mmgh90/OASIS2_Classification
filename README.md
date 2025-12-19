# Explainable Machine Learning for Longitudinal Dementia Status Prediction: Establishing a Leakage-Free Benchmark

This repository contains the source code for the paper **"Explainable machine learning for longitudinal dementia status prediction: establishing a leakage-free benchmark"**.

This study establishes a rigorous, leakage-free framework for predicting dementia status using the OASIS-2 longitudinal MRI dataset. It addresses common pitfalls in longitudinal machine learning, specifically target leakage (by excluding CDR scores) and subject leakage (by employing group-aware splitting).

## Repository Contents

* **`1_Preprocessing_OASIS2.ipynb`**:
    * **Data Cleaning & Leakage Prevention**: Handles missing value imputation and explicitly removes `CDR` (Clinical Dementia Rating) to prevent target leakage.
    * **Feature Engineering**: Creates longitudinal dynamic features, including visit-to-visit changes, cumulative changes, and rates of change for neuroimaging and clinical markers.
    * **Output**: Generates the `processed_dataset.csv`.

* **`2_SVC_Classifier_OASIS2.ipynb`**:
    * **Model Pipeline**: Implements the Support Vector Classifier (SVC) with a rigorous nested validation pipeline.
    * **Optimization**: Includes Random Search for hyperparameter tuning.
    * **Evaluation**: Outputs performance metrics (ROC-AUC, Precision-Recall) and permutation feature importance.

* **`3_LGBM_Classifier_OASIS2.ipynb`**:
    * **Model Pipeline**: Implements the LightGBM gradient boosting classifier.
    * **Explainability**: Includes SHAP (SHapley Additive exPlanations) analysis to interpret model decisions and feature contributions.

## How to Reproduce

### 1. Prerequisites
Ensure you have Python 3.8+ installed. You will need the following libraries:
```bash
pip install pandas numpy scikit-learn lightgbm shap matplotlib seaborn imbalanced-learn openpyxl
