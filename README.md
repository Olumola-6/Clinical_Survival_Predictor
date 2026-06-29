# Clinical Health Data Analysis & Survival Predictor

This project analyzes clinical tumor characteristics to identify key risk factors and builds a logistic regression model to predict patient outcomes with 87.7% accuracy.

## Project Goal
To demonstrate how standard data analysis (similar to Excel pivot tables or Power BI matrices) can be adapted into a Python workflow, focusing on data cleaning, exploratory analysis, and the creation of an interpretable predictive model for a medical screening context.

## Key Objectives & Methodology

### Phase 1: Data Cleaning & Exploratory Analysis

1.  **Data Loading & Inspection:** Load the dataset and inspect data types to ensure numerical consistency.
2.  **Missing Data Audit:** Perform a systematic check for null or invalid values across all records.
3.  **Group Aggregation:** Group patients by their clinical outcome (Malignant/Benign) to calculate average physical traits, replicating the function of a pivot table.
4.  **Correlation Analysis:** Quantify the linear relationship between tumor traits and patient outcomes using a correlation matrix.



## Visuals
<img width="695" height="571" alt="Heatmap chart" src="https://github.com/user-attachments/assets/86662117-db7c-4edc-bd62-5960edef2449" />

### Phase 2: Predictive Modeling

1.  **Data Splitting:** Randomly split the data, holding out 20% of records as a test set to evaluate model performance on unseen data.
2.  **Feature Standardization:** Standardize all features using StandardScaler to ensure that variables measured on different scales (e.g., perimeter vs. smoothness) contribute equally to the model.
3.  **Model Training:** Train a LogisticRegression classifier. This model was chosen for its interpretability, allowing clinicians and researchers to trace the decision-making process.
4.  **Performance Evaluation:** Assess model accuracy using a confusion matrix to break down correct and incorrect predictions.

## Results & Performance

### 1. Key Metrics Comparison

The analysis revealed distinct physical differences between malignant and benign cases, with size-related traits (radius, perimeter) showing the strongest association with outcome.

| Patient Outcome | Average Radius (mm) | Average Perimeter (mm) | Average Texture |
| :--- | :--- | :--- | :--- |
| Malignant | 17.46 | 115.36 | 21.60 |
| Benign | 12.15 | 78.08 | 17.91 |




### 2. Model Performance on Test Set (n=114)

- **Overall Accuracy:** 87.72%
- **Confusion Matrix Breakdown:**
    - True Positives (Malignant correctly identified): 38
    - True Negatives (Benign correctly identified): 62
    - False Positives (Benign incorrectly predicted as Malignant): 10
    - False Negatives (Malignant missed and predicted as Benign): 4

> Note: In a healthcare context, False Negatives (missing a serious case) are considered the most critical error. The model successfully minimized this to 4 out of 114 cases.

## Tools Used
- **Language:** Python
- **Libraries:**
    - **pandas:** Data manipulation and table management.
    - **scikit-learn:** Model training, data splitting, and standardization.
    - **seaborn & matplotlib:** Data visualization (optional, for generating charts).

## Quick Start
1. Clone the repo: `git clone https://github.com/Olumola-6/Clinical-Survival-Predictor.git`
2. Open `clinical_survival_prediction-checkpoint.ipynb` in Jupyter Notebook and click "Run All".
