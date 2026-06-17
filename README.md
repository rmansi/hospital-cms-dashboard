# Hospital Cost & Outcome Dashboard

> Visual analytics and predictive modeling on real federal CMS healthcare data — integrating three government datasets to model hospital excess readmissions and surface the cost/quality drivers behind them.

**Stack:** Python · pandas · scikit-learn · Random Forest · Matplotlib/Seaborn · dashboard/visual analytics
**Domain:** Healthcare · Big Data · Predictive modeling · Visual analytics

---

## Problem
Hospital readmissions are a major cost and quality signal, and CMS penalizes facilities with excess readmissions. The goal: integrate disparate federal datasets to predict a hospital's **Excess Readmission Ratio** and explain which cost and payment factors drive it.

## Data
Three public **CMS** datasets joined into one analytical table:
- **HRRP** (Hospital Readmissions Reduction Program)
- **Medicare Inpatient Providers**
- **Hospital General Information**

Joined on the **6-digit CMS Certification Number (CCN)** — standardized to string with zero-padding to make the key consistent across sources. HRRP was aggregated to hospital level (mean Excess/Predicted/Expected Readmission rates).

## Approach
- **Data engineering:** ingestion, cleaning of monetary fields, inner-join merge on CCN, and engineered **cost-ratio features**.
- **Modeling:** Multiple Linear Regression (5-fold repeated CV) vs. **Random Forest Regressor with GridSearch tuning**.
- **Interpretation:** Random Forest feature importances + residual diagnostics (heteroscedasticity checks).
- **Visualization:** interactive dashboard of cost vs. outcome metrics by hospital.

## Results
- **Random Forest outperformed linear regression** — lower RMSE and higher R² on the test set.
- Most important predictors: **payment metrics, engineered cost ratios, and readmission predictors**.
- Residuals centered around zero, indicating reasonable model fit.

## My role
Team of 3 (IMSE 586 Big Data Analytics & Visualization). Contributed to data ingestion/merging, feature engineering, modeling, and the dashboard.

## Reports
Proposal, progress report, and final write-up are in this folder.
