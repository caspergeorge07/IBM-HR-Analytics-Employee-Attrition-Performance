# IBM HR Analytics Employee Attrition & Workforce Intelligence Project

## End-to-End HR Analytics, Workforce Segmentation, and Attrition Prediction

---

# Project Overview

Employee attrition is one of the most expensive workforce challenges organisations face. High employee turnover increases:

- recruitment costs,
- onboarding costs,
- productivity loss,
- operational disruption,
- and knowledge drain.

The goal of this project was to build a complete workforce analytics pipeline capable of:

1. Understanding patterns behind employee attrition  
2. Identifying high-risk employee groups  
3. Segmenting employees into workforce personas  
4. Predicting employee attrition using machine learning  
5. Improving minority class detection using imbalance handling techniques  
6. Delivering actionable HR retention recommendations  

This project was developed as part of the TS Academy Capstone Project using the IBM HR Analytics Employee Attrition dataset.

---

# Business Problem

The organisation wants to proactively identify employees who are at risk of leaving before resignation occurs.

Traditional HR reporting often explains attrition after employees have already left. This project aims to shift workforce analytics from:

- reactive HR reporting

to:

- proactive workforce intelligence.

The final solution combines:

- exploratory analytics,
- clustering,
- predictive modelling,
- imbalance handling,
- and business storytelling

into a complete employee attrition intelligence system.

---

# Project Objectives

The main objectives of this project were to:

- Perform exploratory data analysis on employee workforce data
- Engineer meaningful workforce-related features
- Segment employees into workforce personas using clustering
- Predict employee attrition using classification models
- Improve minority class detection using imbalance handling techniques
- Compare multiple machine learning models
- Connect clustering and classification insights together
- Produce strategic HR recommendations
- Deliver a portfolio-ready business analytics solution

---

# Dataset Information

## Dataset Used

- IBM HR Analytics Employee Attrition Dataset

## Target Variable

- Attrition
  - Yes = employee left
  - No = employee stayed

## Dataset Features Included

- Demographics
- Compensation information
- Career progression
- Work-life balance
- Satisfaction metrics
- Job role information
- Overtime exposure
- Business travel behaviour
- Organisational tenure

---

# Tools and Technologies

## Programming & Analysis

- Python
- Jupyter Notebook
- SQLite

## Data Manipulation

- Pandas
- NumPy

## Visualisation

- Matplotlib
- Seaborn

## Machine Learning

- Scikit-learn
- XGBoost
- Imbalanced-learn (SMOTE)

## Version Control

- Git
- GitHub

---

# Repository Structure

```text
IBM-HR-Analytics-Employee-Attrition/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── IBM_HR_Attrition_Project.ipynb
│
├── reports/
│   ├── classification_model_comparison.csv
│   └── cluster_attrition_summary.csv
│
├── models/
│   ├── baseline_logistic_regression_model.pkl
│   └── baseline_xgboost_model.pkl
│
├── images/
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

# Project Workflow

The project followed a full end-to-end data science workflow.

## 1. Data Foundation

Performed:

- data loading,
- SQL integration,
- exploratory data analysis,
- missing value inspection,
- duplicate checks,
- data quality assessment.

### SQL Queries Included

- Attrition by department
- Average income by job role
- Overtime distribution analysis

---

## 2. Feature Engineering

Created business-focused engineered features including:

- Age Groups
- Income Bands
- Overtime Risk Indicators
- Work-Life Satisfaction Score
- Income Growth Potential

The feature engineering stage helped transform raw HR variables into more interpretable workforce intelligence metrics.

---

## 3. Employee Segmentation (K-Means Clustering)

Employees were segmented into workforce personas using:

- K-Means clustering
- Elbow Method
- Silhouette Scores
- PCA visualisation

### Final Clusters Included

| Cluster Persona | Attrition Risk |
|---|---|
| Early-Career Flight Risk Employees | Very High |
| Compensation-Sensitive Retention Risk Employees | High |
| Moderately Stable Mid-Career Employees | Medium |
| Stable Long-Tenure Employees | Low |
| Stable Experienced Core Employees | Very Low |

---

# Clustering Insights

The clustering analysis revealed that attrition risk is not evenly distributed across the workforce.

## Key Findings

### Early-Career Flight Risk Employees

- Highest attrition rate (~40%)
- Lowest average monthly income
- Shortest organisational tenure
- High vulnerability to external opportunities

### Stable Experienced Core Employees

- Lowest attrition rate (~7%)
- Highest compensation levels
- Longest organisational tenure
- Strong organisational attachment

### Compensation-Sensitive Employees

- Large workforce segment
- Elevated attrition risk
- Compensation-related vulnerability

These findings demonstrated that workforce segmentation provides strategic insight beyond simple prediction.

---

# Classification Modelling

Multiple classification models were trained and evaluated.

## Models Tested

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting
5. XGBoost

## Evaluation Metrics

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

# Baseline Classification Results

| Model | ROC-AUC | Recall | F1 Score |
|---|---|---|---|
| Logistic Regression | 0.83 | 0.34 | 0.45 |
| Gradient Boosting | 0.79 | Moderate | Moderate |
| Random Forest | 0.78 | Low | Moderate |
| XGBoost | 0.76 | Moderate | Moderate |
| Decision Tree | 0.58 | Weak | Weak |

## Key Finding

Logistic Regression achieved the strongest overall balance between:

- predictive performance,
- recall,
- interpretability,
- and business transparency.

---

# Feature Importance Insights

The most important attrition drivers across models included:

- Overtime
- Monthly Income
- Total Working Years
- Years At Company
- Business Travel
- Work-Life Balance
- Job Satisfaction
- Career Stage

## Business Interpretation

Employees were more likely to leave when they experienced:

- lower compensation,
- excessive overtime,
- weaker organisational attachment,
- limited progression,
- and lower satisfaction.

---

# Imbalance Handling

The dataset contained a significant class imbalance problem:

- Employees who stayed: ~84%
- Employees who left: ~16%

To improve minority class detection, the following techniques were applied:

- Class Weighting
- Threshold Tuning
- SMOTE Oversampling

---

# Imbalance Handling Results

| Strategy | Precision | Recall | F1 Score |
|---|---|---|---|
| Baseline Logistic Regression | 0.67 | 0.34 | 0.45 |
| Class Weighted Logistic Regression | 0.38 | 0.68 | 0.49 |
| SMOTE Logistic Regression | 0.40 | 0.66 | 0.50 |

## Key Finding

SMOTE produced the strongest balance between:

- recall,
- precision,
- and F1 score.

This significantly improved the model's ability to identify employees at risk of leaving.

---

# Precision vs Recall Tradeoff

A major challenge in attrition prediction is balancing:

- identifying employees likely to leave (recall),
- while avoiding excessive false alarms (precision).

From a business perspective:

- false negatives are costly because employees leave unexpectedly,
- while false positives may create unnecessary HR intervention effort.

The project prioritised recall and F1 score because proactive retention planning is more valuable than maximising accuracy alone.

---

# Clustering and Classification Tie-In

One of the strongest aspects of this project was integrating:

- clustering analysis,
- and classification modelling.

## Classification Answered

> "Who is likely to leave?"

## Clustering Answered

> "What type of employees are likely to leave?"

This created a more actionable workforce intelligence system capable of supporting:

- targeted HR interventions,
- strategic workforce planning,
- and retention prioritisation.

---

# Business Recommendations

## 1. Prioritise Early-Career Retention

High-risk early-career employees require:

- mentorship programmes,
- clearer career pathways,
- stronger onboarding support,
- and compensation review.

---

## 2. Reduce Overtime Risk

Overtime consistently appeared as one of the strongest attrition predictors.

HR should:

- monitor workload exposure,
- reduce burnout risk,
- and improve work-life balance.

---

## 3. Improve Compensation Transparency

Compensation-sensitive employee groups demonstrated elevated turnover risk.

Recommendations:

- salary benchmarking,
- reward structure review,
- promotion transparency.

---

## 4. Strengthen Career Development

Employees with weaker organisational attachment showed higher attrition risk.

HR should:

- improve internal mobility,
- provide growth pathways,
- and strengthen employee engagement.

---

# Ethical Considerations

Employee attrition models should be implemented responsibly.

Important considerations include:

- employee privacy,
- fairness,
- bias monitoring,
- transparency,
- and human oversight.

The model should support HR decision-making rather than replace human judgement.

---

# Project Limitations

## Dataset Limitations

- The IBM HR dataset is synthetic.
- No employee sentiment data was available.
- No resignation reasons were included.
- Temporal workforce history was limited.

## Modelling Limitations

- Advanced hyperparameter tuning was limited.
- Deep learning models were not explored.
- External labour market variables were unavailable.

---

# Future Improvements

Potential future improvements include:

- SHAP explainability analysis
- Real-time dashboard deployment
- Survival analysis
- Deep learning experimentation
- Employee sentiment integration
- Power BI or Streamlit deployment
- Real-time HR monitoring systems

---

# Final Business Conclusion

This project demonstrated how machine learning and workforce analytics can support strategic HR decision-making.

By combining:

- clustering,
- predictive modelling,
- imbalance handling,
- and business interpretation,

this project successfully identified:

- which employees are likely to leave,
- what type of employees are most vulnerable,
- and what HR interventions should be prioritised.

The final solution transformed raw HR data into a practical workforce intelligence system capable of supporting:

- proactive employee retention,
- workforce segmentation,
- targeted intervention planning,
- and data-driven HR strategy.

---

# How to Run the Project

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

## 2. Navigate Into the Project

```bash
cd IBM-HR-Analytics-Employee-Attrition
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

---

# Requirements

Main dependencies include:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
imbalanced-learn
jupyter
```

---

# Author

Ndubuaku George Ekwueme

MSc Data Science | Data Analyst | Machine Learning Enthusiast

Focused on:

- workforce analytics,
- predictive modelling,
- business intelligence,
- and applied machine learning.

---

# Portfolio Highlights

This project demonstrates:

- end-to-end machine learning workflow,
- business storytelling,
- clustering and classification integration,
- imbalance handling,
- strategic HR analytics,
- and portfolio-ready analytical communication.

## Additional Documentation

- Technical walkthrough and meeting preparation document:
  - `reports/IBM_HR_Attrition_Project_Technical_Walkthrough.docx`
