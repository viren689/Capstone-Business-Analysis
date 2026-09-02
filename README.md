# Customer Churn Business Analysis

## Week 8 Capstone Project – The Developers Arena

### 1. Project Overview

This capstone project analyzes customer churn data to identify the major factors associated with customer attrition and convert analytical findings into actionable business recommendations.

The project follows an end-to-end data analysis workflow:

**Business Problem → Data Collection → Data Cleaning → Exploratory Data Analysis → Statistical Analysis → Customer Segmentation → Business Insights → Recommendations → Implementation Plan**

The analysis focuses on understanding which customer groups have higher churn risk and how a business can prioritize retention efforts.

---

## 2. Business Problem

Customer churn can negatively affect recurring revenue, customer lifetime value, and business growth.

The business needs to understand:

* How many customers are churning?
* Which contract types have the highest churn?
* Which tenure groups are most vulnerable?
* Does monthly pricing differ between retained and churned customers?
* Which customer segments should receive retention attention?
* What actions can be implemented to reduce churn?

---

## 3. Project Objectives

The main objectives are:

1. Analyze customer churn patterns.
2. Identify important churn-related factors.
3. Compare churn across contract types and tenure groups.
4. Validate important findings using statistical tests.
5. Create customer risk segments.
6. Estimate potential retention impact.
7. Develop practical business recommendations.
8. Present the analysis in a professional business format.

---

## 4. Dataset

The project uses a customer churn dataset containing:

* **500 customers**
* **9 variables**
* Customer demographic and service-related information
* Churn status for each customer

### Main Variables

| Variable         | Description                                |
| ---------------- | ------------------------------------------ |
| CustomerID       | Unique customer identifier                 |
| Tenure           | Number of months the customer has stayed   |
| MonthlyCharges   | Monthly customer charges                   |
| TotalCharges     | Total charges associated with the customer |
| Contract         | Customer contract type                     |
| PaymentMethod    | Customer payment method                    |
| PaperlessBilling | Whether paperless billing is enabled       |
| SeniorCitizen    | Senior citizen indicator                   |
| Churn            | Customer churn indicator                   |

---

## 5. Tools & Technologies

The project was developed using:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Jupyter Notebook
* Git
* GitHub

---

## 6. Project Structure

```text
Week8-Capstone-Business-Analysis/
│
├── capstone_analysis.ipynb
│
├── data/
│   ├── raw_data.csv
│   └── cleaned_data.csv
│
├── notebooks/
│   ├── 1_data_cleaning.ipynb
│   ├── 2_eda.ipynb
│   └── 3_analysis.ipynb
│
├── presentation/
│   └── business_presentation.pptx
│
├── reports/
│   ├── executive_summary.pdf
│   └── technical_report.pdf
│
├── screenshots/
│   ├── 01_overall_churn.png
│   ├── 02_contract_churn.png
│   ├── 03_tenure_churn.png
│   ├── 04_monthly_charges.png
│   ├── 05_contract_tenure.png
│   └── 06_risk_segmentation.png
│
├── README.md
└── requirements.txt
```

---

## 7. Data Cleaning & Validation

The raw dataset was inspected before analysis.

The following checks were performed:

* Dataset dimensions
* Data types
* Missing values
* Duplicate rows
* Duplicate customer IDs
* Unique categorical values
* Numerical value ranges
* Binary variable validation
* Customer ID format validation

### Data Quality Result

* **Rows:** 500
* **Columns:** 9
* **Missing values:** 0
* **Duplicate rows:** 0
* **Duplicate Customer IDs:** 0

The validated dataset was saved as:

```text
data/cleaned_data.csv
```

---

## 8. Exploratory Data Analysis

Multiple analytical techniques and visualizations were used to understand churn patterns.

### Overall Churn

* Retained customers: **447**
* Churned customers: **53**
* Overall churn rate: **10.60%**

### Contract Analysis

| Contract Type  | Customers | Churned | Churn Rate |
| -------------- | --------: | ------: | ---------: |
| Month-to-month |       170 |      35 |     20.59% |
| One year       |       186 |       8 |      4.30% |
| Two year       |       144 |      10 |      6.94% |

Month-to-month customers show the highest observed churn rate.

### Tenure Analysis

| Tenure Group | Customers | Churned | Churn Rate |
| ------------ | --------: | ------: | ---------: |
| 0–12 Months  |        84 |      53 |     63.10% |
| 13–24 Months |        75 |       0 |      0.00% |
| 25–48 Months |       171 |       0 |      0.00% |
| 49+ Months   |       170 |       0 |      0.00% |

The first 12 months are the most critical period in this dataset.

---

## 9. Monthly Charges Analysis

Average monthly charges were compared between retained and churned customers.

| Customer Status | Average Monthly Charges |
| --------------- | ----------------------: |
| Retained        |                  111.72 |
| Churned         |                  129.77 |

The difference is approximately **18.05**.

This indicates that churned customers have higher average monthly charges in this dataset.

---

## 10. Statistical Analysis

Statistical tests were used to validate important observations.

### Independent T-Test – Monthly Charges

* Test statistic: **-2.6464**
* p-value: **0.0101**
* Result: Statistically significant

### Independent T-Test – Tenure

* Test statistic: **34.5349**
* p-value: **< 0.001**
* Result: Statistically significant

### Chi-Square Test – Contract Type

* Chi-square statistic: **27.7153**
* Degrees of freedom: **2**
* p-value: **< 0.001**
* Result: Statistically significant

### Cramér's V

* Cramér's V: **0.2354**
* Interpretation: Moderate association

Statistical significance indicates evidence of an association or difference. It does not prove that one variable directly causes churn.

---

## 11. Customer Risk Segmentation

A rule-based risk score was created using three characteristics:

* Early tenure: 12 months or less
* Higher monthly charges
* Month-to-month contract

### Risk Segments

| Risk Level  | Customers | Churned | Churn Rate |
| ----------- | --------: | ------: | ---------: |
| High Risk   |        21 |      21 |    100.00% |
| Medium Risk |       103 |      30 |     29.13% |
| Low Risk    |       376 |       2 |      0.53% |

The high-risk segment should receive the highest retention priority.

**Important:** This is a rule-based analytical segmentation, not a production machine-learning prediction model.

---

## 12. Highest-Risk Combined Segment

The most critical combined segment is:

**Month-to-month contract + 0–12 months tenure**

Results:

* Customers: **35**
* Churned: **35**
* Observed churn rate: **100%**
* Average monthly charge exposure: **120.94**
* Total monthly charge exposure: **4233.00**

This segment should be prioritized for proactive retention initiatives.

---

## 13. Retention Scenario Analysis

A simple scenario analysis was performed for the 35 customers in the highest-risk combined segment.

| Retention Scenario | Customers Potentially Retained |
| ------------------ | -----------------------------: |
| 20%                |                              7 |
| 30%                |                             10 |
| 40%                |                             14 |

These are scenario estimates based on the observed dataset and should not be interpreted as guaranteed business results.

---

## 14. Key Business Insights

The analysis produced several important insights:

1. Overall observed churn is **10.60%**.
2. Month-to-month customers have the highest contract-level churn rate at **20.59%**.
3. Customers in their first 12 months have an observed churn rate of **63.10%**.
4. All observed churn cases occur within the first 12 months in this dataset.
5. Churned customers have higher average monthly charges.
6. Contract type and tenure show statistically significant relationships with churn.
7. The combination of early tenure and month-to-month contracts represents the highest-priority segment.
8. Risk-based retention can help businesses focus resources on customers with multiple risk indicators.

---

## 15. Business Recommendations

### 1. Strengthen First-Year Onboarding

Introduce structured customer engagement during the first year.

Possible actions:

* 30-day check-in
* 60-day check-in
* 90-day check-in
* Usage education
* Service satisfaction surveys

### 2. Encourage Suitable Customers to Move Beyond Month-to-Month Contracts

Offer relevant incentives for customers who are willing to move to longer contracts.

Possible actions:

* Contract upgrade offers
* Loyalty benefits
* Personalized discounts
* Additional service benefits

### 3. Proactive High-Risk Customer Outreach

Prioritize customers showing multiple risk indicators.

Retention teams can use risk scores to create targeted outreach lists.

### 4. Review Higher Monthly Charges

Investigate whether higher monthly charges are associated with lower perceived value.

Possible actions:

* Personalized plans
* Value-added services
* Pricing reviews
* Customer satisfaction checks

### 5. Monitor Retention KPIs

Track:

* Monthly churn rate
* 12-month churn rate
* High-risk churn rate
* Medium-risk churn rate
* Contract conversion rate
* Campaign response rate
* Number of customers retained

---

## 16. Implementation Plan

| Phase   | Action                            | KPI                  |
| ------- | --------------------------------- | -------------------- |
| Phase 1 | Identify high-risk customers      | High-risk population |
| Phase 2 | Improve first-year onboarding     | 12-month churn       |
| Phase 3 | Target month-to-month customers   | Contract conversion  |
| Phase 4 | Run proactive retention campaigns | Campaign response    |
| Phase 5 | Test personalized offers          | Retention uplift     |
| Phase 6 | Monitor results                   | Overall churn        |

Retention campaigns should be tested before being scaled across the entire customer base.

---

## 17. Limitations

The analysis has several limitations:

* The dataset contains only 500 customers.
* The dataset appears to have synthetic/training-data characteristics.
* The available variables are limited.
* The unusually perfect early-tenure churn pattern may not represent real-world behavior.
* Statistical association does not establish causation.
* The risk score is rule-based and is not a production predictive model.
* The dataset does not specify currency, so charge exposure is reported as dataset units rather than a specific currency.

---

## 18. Reproducibility

The project is organized into separate notebooks for better readability and modularity:

1. `1_data_cleaning.ipynb` – Data loading, validation, and cleaning
2. `2_eda.ipynb` – Exploratory analysis, visualizations, and statistical tests
3. `3_analysis.ipynb` – Advanced segmentation and business impact analysis
4. `capstone_analysis.ipynb` – End-to-end capstone summary

Required Python packages are listed in:

```text
requirements.txt
```

---

## 19. Project Deliverables

The completed project includes:

* Cleaned dataset
* Data-cleaning notebook
* EDA notebook
* Advanced analysis notebook
* Capstone notebook
* Executive summary PDF
* Technical report PDF
* Business presentation
* Analysis visualizations
* README documentation

---

## 20. Conclusion

This capstone demonstrates an end-to-end approach to solving a real-world business analytics problem.

The analysis identified **early customer tenure** and **month-to-month contracts** as the most important practical areas for retention focus. Statistical testing supports significant differences and associations for tenure, monthly charges, and contract type.

The most actionable strategy is to combine early-tenure onboarding, contract conversion initiatives, and proactive risk-based retention campaigns.

The next step for a real business would be to validate these findings using a larger production dataset, measure campaign performance, and develop a predictive churn model for scalable customer-level decision making.
