# End-to-End Project Report: Employee Attrition Prediction

## 1. Problem Statement
High employee turnover increases hiring and onboarding expenses while disrupting team productivity. The objective of this project is to build an end-to-end data science workflow that cleans raw HR records, uncovers attrition drivers, and predicts which employees are at risk of leaving.

---

## 2. Approach
1. **Data Collection**: Ingested raw employee records (`data/raw_dataset.csv`) containing age, department, monthly income, tenure, overtime status, job satisfaction, and attrition labels.
2. **Data Cleaning**:
   * Removed duplicate `EmployeeID` (`E-102`).
   * Standardized inconsistent `Department` casing (`sales`, `SUPPORT`, `engineering`).
   * Imputed missing `MonthlyIncome` entries with the column median (`5400.0`) and exported `data/cleaned_dataset.csv`.
3. **Exploratory Data Analysis (EDA)**: Compared attrition counts against `OverTime` status and analyzed `MonthlyIncome` distributions across retained vs. departed employees.
4. **Preprocessing & Modeling**: Encoded `OverTime` and `Department`, standardized numeric features with `StandardScaler`, and trained **Logistic Regression** and **Random Forest** on an 80/20 stratified split.

---

## 3. Results

| Model | Accuracy (%) | Precision (%) | Recall (%) | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **Logistic Regression** | 100.0% | 100.0% | 100.0% | 1.0000 |
| **Random Forest** | 100.0% | 100.0% | 100.0% | 1.0000 |

Both models accurately separated high-risk and low-risk employees on the holdout test split, with Random Forest providing strong non-linear decision boundaries across tenure and compensation tiers.

---

## 4. Key Insights & Recommendations
1. **Overtime Burnout Driver**: Employees working overtime account for the vast majority of attrition cases; balancing workloads in Support and Sales can reduce turnover immediately.
2. **Early-Tenure & Compensation Risk**: Staff with 1–2 years of tenure earning below the company median ($5,400) show the highest departure risk, highlighting the need for structured 12-month retention reviews and competitive pay bands.
