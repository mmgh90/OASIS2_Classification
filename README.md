# Explainable Machine Learning for Longitudinal Dementia Status Prediction: Establishing a Leakage-Free Benchmark

This repository contains the source code for the paper **"Explainable machine learning for longitudinal dementia status prediction: establishing a leakage-free benchmark"**.

This study establishes a rigorous, leakage-free framework for predicting dementia status using the OASIS-2 longitudinal dataset. It addresses common pitfalls in longitudinal machine learning, specifically target leakage (by excluding CDR scores) and subject leakage (by employing group-aware splitting).

## Repository Contents

* **`1_Preprocessing_OASIS2.ipynb`**:
    * **Data Cleaning & Leakage Prevention**: Handles missing value imputation and explicitly removes `CDR` (Clinical Dementia Rating) to prevent target leakage.
    * **Feature Engineering**: Creates longitudinal dynamic features, including visit-to-visit changes, cumulative changes, and rates of change for neuroimaging and clinical markers.
    * **Output**: Generates the `processed_dataset.csv`.

* **`2_SVC_Classifier_OASIS2.ipynb`**:
    * Implements the Support Vector Classifier (SVC) with a validation pipeline.

* **`3_LGBM_Classifier_OASIS2.ipynb`**:
    * Implements the LightGBM gradient boosting classifier.

## Data Access & Setup

Due to licensing restrictions, the OASIS-2 dataset cannot be hosted directly in this repository.

1.  **Download Data**: Request access and download the OASIS-2 longitudinal dataset (Excel format) from [OASIS Brains](https://www.oasis-brains.org/).
2.  **Create Data Folder**: Create a folder named `data` in the root directory of this repository.
3.  **Place File**: Move the downloaded Excel file into the `data/` folder and ensure the filename matches the path in `1_Preprocessing_OASIS2.ipynb` (or update the notebook path to match your filename).

## Execution Order

Now, run the notebooks in the following order:

1.  Run **`1_Preprocessing_OASIS2.ipynb`** first. This will generate the clean `processed_dataset.csv` inside the `data/` folder.
2.  Run **`2_SVC_Classifier_OASIS2.ipynb`** or **`3_LGBM_Classifier_OASIS2.ipynb`** to train and evaluate the models using the processed data.


## License

This project is licensed under the MIT License - see the LICENSE file for details.
