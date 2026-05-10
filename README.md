# IBM HR Analytics Employee Attrition — TS Academy Capstone Project

## Project Overview

This project investigates employee attrition using the IBM HR Analytics Employee Attrition dataset. The company wants to understand the patterns behind employee turnover, segment employees into meaningful groups, and build predictive models that can identify employees who may be at risk of leaving.

The project follows a full analytics and machine learning pipeline:

1. Data loading and SQL-based exploration
2. Exploratory data analysis and data quality checks
3. Feature engineering, encoding, and scaling
4. K-Means clustering and employee segmentation
5. Supervised classification modelling
6. Imbalance handling using class weighting, threshold tuning, and SMOTE
7. Clustering-classification tie-in
8. Business recommendations and final conclusions

---

## Business Problem

Employee attrition can increase recruitment costs, reduce productivity, disrupt team performance, and lead to the loss of organisational knowledge. This project aims to help HR teams move from reactive retention management to proactive workforce risk monitoring.

The core questions answered are:

- Which employee characteristics are associated with attrition?
- Can employees be segmented into meaningful workforce personas?
- Which employee groups have the highest attrition risk?
- Which model should be used to predict attrition?
- What practical retention actions should HR prioritise?

---

## Dataset

**Dataset:** IBM HR Analytics Employee Attrition Dataset  
**Target variable:** `Attrition`  
**Positive class:** `Attrition = 1`, employee left  
**Negative class:** `Attrition = 0`, employee stayed

The dataset includes employee information such as income, job role, department, overtime, satisfaction scores, years at company, total working years, and other HR-related variables.

---

## Repository Structure

```text
.
├── data/
│   ├── raw/
│   │   └── WA_Fn-UseC_-HR-Employee-Attrition.csv
│   └── processed/
│       ├── hr_attrition_clean_day1.csv
│       ├── hr_attrition_feature_engineered.csv
│       └── hr_attrition_clustered.csv
│
├── models/
│   ├── baseline_logistic_regression_model.pkl
│   └── baseline_xgboost_model.pkl
│
├── notebooks/
│   ├── 01_data_foundation.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_clustering.ipynb
│   ├── 04_classification.ipynb
│   ├── 05_imbalance_handling.ipynb
│   └── 06_final_capstone.ipynb
│
├── reports/
│   └── classification_model_comparison.csv
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Methodology

### 1. Data Foundation

The dataset was loaded, inspected, and pushed into SQLite for SQL-based exploration. Data quality checks were performed for missing values, duplicates, constant columns, target distribution, and early attrition patterns.

### 2. Feature Engineering and Encoding

New business-driven features were created to improve interpretability and modelling performance, including:

- Age groups
- Income bands
- Years-at-company groups
- Overtime risk indicator
- Work-life satisfaction score
- Income growth potential

Categorical variables were encoded and numerical variables were scaled for clustering and machine learning.

### 3. Clustering Analysis

K-Means clustering was used to segment employees into personas. K values from 2 to 10 were tested using elbow and silhouette analysis. K = 5 was selected because it provided the strongest balance between interpretability and business actionability.

Final personas included:

- Early-Career Flight Risk Employees
- Compensation-Sensitive Retention Risk Employees
- Moderately Stable Mid-Career Employees
- Stable Experienced Core Employees
- Stable Long-Tenure Employees

### 4. Classification Modelling

Five classification models were trained and compared:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost

Models were evaluated using accuracy, precision, recall, F1 score, and ROC-AUC.

### 5. Imbalance Handling

Because attrition was the minority class, imbalance handling techniques were applied:

- Majority-class baseline comparison
- Class weighting
- Threshold tuning
- SMOTE oversampling

The focus was on improving recall and F1 score for employees who actually left.

### 6. Tie-In Analysis

Cluster labels were connected back to classification insights to understand which employee personas were most likely to leave and why. This helped translate model outputs into actionable HR retention strategies.

---

## Key Findings

- Attrition was not evenly distributed across the workforce.
- Early-career employees had the highest attrition risk.
- Compensation-sensitive employees represented the largest workforce risk due to their size and elevated attrition rate.
- Stable experienced employees had the lowest attrition risk.
- Important predictors included income, overtime, total working years, age, tenure, business travel, and satisfaction-related features.
- Logistic Regression provided the strongest baseline balance between performance and interpretability.
- SMOTE improved the balance between recall and precision for attrition detection.

---

## Final Model Recommendation

The recommended production approach is a Logistic Regression model enhanced with imbalance handling.

This model was selected because it provides:

- Strong interpretability for HR stakeholders
- Competitive ROC-AUC performance
- Improved recall after imbalance handling
- Clear business explanation through coefficients
- Practical suitability for employee risk monitoring

---

## Business Recommendations

HR should prioritise:

1. **Early-career retention** through improved onboarding, mentoring, and career development.
2. **Compensation reviews** for lower-income and compensation-sensitive employee segments.
3. **Overtime monitoring** to reduce burnout and workload pressure.
4. **Career progression transparency** to reduce stagnation and improve retention.
5. **Persona-based interventions** rather than generic company-wide retention strategies.

---

## Ethical Considerations

Attrition prediction should support employee wellbeing and workforce planning. It should not be used to penalise employees. Any real-world deployment should include:

- Human oversight
- Bias monitoring
- Employee privacy protection
- Transparent use of predictions
- Fairness checks across demographic groups

---

## How to Run the Project

1. Clone the repository.
2. Create a virtual environment.
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Run the notebooks in order from the `notebooks/` folder:

```text
01_data_foundation.ipynb
02_feature_engineering.ipynb
03_clustering.ipynb
04_classification.ipynb
05_imbalance_handling.ipynb
06_final_capstone.ipynb
```

The notebooks use relative paths and should be run from inside the `notebooks/` directory.

---

## Portfolio Summary

This project demonstrates a complete end-to-end data analytics and machine learning workflow for HR attrition prediction. It combines SQL, exploratory analysis, feature engineering, clustering, classification, imbalance handling, model interpretation, and business recommendations into a single portfolio-ready case study.
