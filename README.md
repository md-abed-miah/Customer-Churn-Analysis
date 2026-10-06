# 📊 Customer Churn Analysis

An exploratory data analysis project focused on understanding **customer churn in a telecom company**.

The goal of this project is to identify **which customers are most likely to leave, what factors are associated with churn, and what the business can do to improve customer retention.**

---

## 📌 Project Overview

Customer churn is one of the biggest challenges for subscription-based businesses.

In this project, I analyzed a telecom customer dataset containing **7,043 customers** and explored factors such as:

* Contract type
* Payment method
* Internet service
* Tenure
* Monthly charges
* Customer churn

The analysis focuses on finding patterns in customer behavior and turning those patterns into **actionable business insights**.

---

## 🎯 Business Questions

This project aims to answer:

1. What is the overall customer churn rate?
2. Does contract type affect customer churn?
3. Which payment method has the highest churn?
4. Does internet service type influence churn?
5. Are new customers more likely to leave?
6. Do customers with higher monthly charges churn more?
7. Which customer segments are at the highest risk of churn?
8. What actions could the company take to improve customer retention?

---

## 🛠️ Tools & Technologies

* **Python**
* **Pandas** — Data cleaning and analysis
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **Jupyter Notebook / Kaggle Notebook**

---

## 🧹 Data Cleaning

Before starting the analysis, I performed several preprocessing steps:

* Converted `TotalCharges` from text to numeric
* Converted `Churn` from `Yes/No` into `1/0`
* Checked missing values
* Checked duplicate records
* Reviewed data types and descriptive statistics
* Created additional groups for tenure and monthly charges

Example:

```python
churn_data["TotalCharges"] = pd.to_numeric(
    churn_data["TotalCharges"],
    errors="coerce"
)

churn_data["Churn"] = churn_data["Churn"].map({
    "Yes": 1,
    "No": 0
})
```

---

## 📈 Exploratory Data Analysis

### 1. Overall Churn

The overall churn rate is approximately **26%**, meaning roughly **1 in 4 customers** has left the company.

This provides a baseline for comparing different customer segments.

---

### 2. Churn by Contract Type

Contract type shows a strong relationship with customer churn.

**Month-to-month customers have significantly higher churn rates** compared with customers on one-year or two-year contracts.

This suggests that customers with longer-term commitments are generally more likely to remain with the company.

---

### 3. Churn by Payment Method

Customers using **electronic check** show the highest churn rate among the payment methods analyzed.

Customers using automatic payment methods generally show lower churn.

This suggests that payment behavior and convenience may be associated with customer retention.

---

### 4. Churn by Internet Service

One of the interesting findings is that **fiber optic customers have a higher churn rate than DSL customers**.

Since fiber is generally positioned as a premium service, this may indicate potential issues related to:

* Pricing
* Customer expectations
* Service quality
* Customer experience

Further analysis would be required to determine the exact cause.

---

### 5. Churn by Tenure

New customers are more likely to churn.

Customers in their **first year** show significantly higher churn compared with customers who have stayed longer.

This indicates that the **first 12 months are an important retention period**.

---

### 6. Monthly Charges and Churn

Customers with higher monthly charges tend to show higher churn rates.

This suggests that customers paying more may have higher expectations regarding service quality and overall value.

---

## 🔎 High-Risk Customer Segment

I created a high-risk customer segment using three conditions:

```python
high_risk = churn_data[
    (churn_data["Contract"] == "Month-to-month") &
    (churn_data["tenure"] < 12) &
    (churn_data["MonthlyCharges"] >
     churn_data["MonthlyCharges"].median())
]
```

This segment consists of customers who are:

* On a month-to-month contract
* In their first year
* Paying above the median monthly charge

These customers could be considered a **high-priority retention segment**.

---

## 📊 Visualizations

The project includes visualizations for:

* Overall churn distribution
* Churn rate by contract type
* Churn rate by payment method
* Churn rate by internet service
* Churn rate by tenure group
* Churn rate by monthly charge
* Contract × Internet Service churn heatmap
* Monthly charge distribution by churn status

### 🎯 Final Dashboard

A consolidated dashboard brings the major findings together into a single view for easier interpretation.

---

## 💡 Key Insights

### 1. Churn is a significant business problem

Approximately **26% of customers churned**, making customer retention an important business priority.

### 2. Contract type is strongly associated with churn

Month-to-month customers are considerably more likely to churn than customers with longer-term contracts.

### 3. Electronic check customers show higher churn

Customers using electronic checks have the highest churn rate among the payment methods analyzed.

### 4. Fiber customers show relatively high churn

Fiber optic customers have a higher churn rate than DSL customers, suggesting that pricing, service quality, or customer expectations may require further investigation.

### 5. New customers are more vulnerable

Customers with shorter tenure are more likely to leave, making the first year an important period for retention efforts.

### 6. Higher monthly charges are associated with higher churn

Customers paying more per month appear to have a higher likelihood of leaving.

---

## 🎯 Business Recommendations

Based on the analysis, the company could consider:

### 🔹 1. Encourage Long-Term Contracts

Offer targeted incentives to month-to-month customers to move toward one-year or two-year contracts.

### 🔹 2. Improve First-Year Retention

Create onboarding and retention programs specifically for customers during their first 12 months.

### 🔹 3. Promote Automatic Payments

Encourage customers to use automatic payment methods through incentives or simplified enrollment.

### 🔹 4. Investigate Fiber Customer Experience

Analyze fiber pricing, service quality, support tickets, complaints, and customer satisfaction to understand why churn is relatively high.

### 🔹 5. Target High-Risk Customers

Use customer attributes to identify high-risk segments and provide personalized retention offers before customers decide to leave.

---

## 📂 Project Structure

```text
customer-churn-analysis/
│
├── Customer_Churn_Analysis.ipynb
├── churn_data.csv
├── README.md
└── images/
    ├── churn_distribution.png
    ├── contract_churn.png
    ├── payment_churn.png
    ├── internet_churn.png
    └── final_dashboard.png
```

---

## 🚀 Future Improvements

This project currently focuses on **exploratory data analysis**.

Future improvements could include:

* Building a machine learning model to predict churn
* Feature importance analysis
* Customer segmentation
* Churn prediction scoring
* Retention campaign simulation
* Customer Lifetime Value analysis
* Interactive dashboard using **Power BI**
* Statistical testing to validate relationships between variables

---

## 🧠 What I Learned

Through this project, I practiced:

* Data cleaning with Pandas
* Exploratory Data Analysis (EDA)
* Group-by analysis
* Customer segmentation
* KPI calculation
* Data visualization
* Identifying business patterns from data
* Translating analytical findings into business recommendations

---

## 👨‍💻 Author

**Md. Abed Miah**
Data Analyst | Python & Excel Dashboard Developer

📧 [oficialabed@gmail.com](mailto:oficialabed@gmail.com)
📱 +880 1731122699
🔗 [LinkedIn](https://linkedin.com/in/md-abed-miah)
💻 [GitHub](https://github.com/md-abed-miah)

---

⭐ If you find this project useful, feel free to explore the notebook and share your feedback.
