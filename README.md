# Employee Attrition Analytics & Early Warning Dashboard

## 1. Background and Objective

**Background:** Company XYZ is currently facing a critical employee attrition rate of **16.1%**, which significantly exceeds the healthy industry benchmark of **10%**. This high turnover is imposing substantial recruitment costs, eroding institutional knowledge, and reducing team productivity.

**Objectives:** * Develop a data-driven machine learning model to predict employee attrition risk and identify key influencing factors.

* Reduce the overall attrition rate to the **10%** target level within the next year.
* Deploy an **"Early Warning Dashboard"** to provide real-time risk scores and model interpretability for HR decision-making.



## 2. Problem Scope

The project focuses on:

* **Target Population:** 4,410 employee records including demographics, job details, and survey responses.
* **Analysis Segments:** Departmental, job role, and risk cohort breakdowns.
* **Model Goal:** Transitioning HR from reactive talent management to a proactive, predictive approach.



## 3. Data and Assumptions

**Data Source:** The analysis uses the **HR Analytics Case Study** dataset, comprising 4,410 rows and 30 columns across several tables: `general_data`, `employee_survey_data`, `manager_survey_data`, and time logs.

**Assumptions:**

* **Success Rate:** A 50% success rate for targeted retention interventions is assumed for business impact calculations.
* **Financial Impact:** Replacement costs are estimated at 1.5x the employee's yearly salary, with a standard intervention cost of $2,000 per employee.



## 4. Data Analysis

* **Data Preparation:** Handled missing values via median imputation and addressed outliers in features like `MonthlyIncome` and `TotalWorkingYears`.
* **Feature Engineering:** Created 13 new features, including `AvgWorkingHours`, `PercentOvertime`, and `CommuteStressIndex` to better capture burnout and engagement signals.
* **Key Drivers Identified:**
* **Workload:** High overtime intensity is a primary driver of burnout.
* **Demographics:** Younger and "Single" employees show higher attrition tendencies.
* **Satisfaction:** Low job and environment satisfaction strongly correlate with leaving.
* **Modeling:** Benchmarked multiple models (Logistic Regression, SVM, Random Forest, etc.). The **Random Forest** model was selected, achieving an accuracy of **99.6%** and a recall of **97.8%** after GridSearchCV and threshold tuning (optimal at 0.32).



## 5. Conclusion

The project successfully developed a high-precision predictive framework.

* The model identified that **overtime intensity**, **marital status (Single)**, **age**, and **low job satisfaction** are the top predictors of attrition.
* By focusing on "High Risk" segments (probability > 0.60), the company can potentially prevent significant turnover-related losses.
* The deployment of the Streamlit dashboard enables HR to perform real-time risk assessment and decision-making.



## 6. Recommendations

* 
**Operationalize Insights:** Shift from offline model development to real-world integration with enterprise HRIS systems.


* **Targeted Interventions:**
* Implement **team-level overtime dashboards** to monitor burnout.


* Design **career acceleration programs** and assign mentors for early-career/single employees.


* Conduct **quarterly pulse checks** to detect dissatisfaction early.




* 
**Policy Adjustments:** Review travel policies and offer hybrid/remote options for high-risk roles with high commute stress.



## 7. Installation and Usage

**Prerequisites:**

* Python 3.x
* Streamlit
* Scikit-Learn, Pandas, NumPy, SHAP

**Installation:**

```bash

# Install dependencies
pip install -r requirements.txt

```

**Usage:**

1. Run the Streamlit app:
```bash
streamlit run app.py

```
2. Access the dashboard via the provided local URL (typically `http://localhost:8501`).
3. Upload employee data or use the sidebar to predict individual attrition risk scores.



---

*Note: This project was completed as part of the DS60 DataForge Final Project.*
