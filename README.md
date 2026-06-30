# 📉 SaaS Churn Analysis   

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

> **Business Question:** Why are customers leaving — and which customer segments are at the highest risk of churning next month?

---

## 📌 Project Overview

Churn is the silent killer of any SaaS business. This project simulates a B2B SaaS company's subscription data and builds a Power BI dashboard that helps the Customer Success and Revenue teams identify churn patterns, at-risk segments, and retention opportunities — before it's too late.

---

## 🎯 Key Business Questions Answered

- What is the overall churn rate and how has it trended over time?
- Which pricing plans have the highest churn?
- Which industries are churning the most?
- What is the Monthly Recurring Revenue (MRR) lost due to churn?
- Which acquisition channels retain customers the longest?

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Power BI | Interactive dashboard and visualization |
| DAX | MRR, churn rate, retention, cohort calculations |
| Excel | Data preparation and cleaning |

---

## 📊 Dashboard Preview

 
 ![Dashboard Preview](Dashboard/Preview.png)


---

## 📈 Key DAX Measures

```dax
-- Churn Rate %
Churn Rate % = 
DIVIDE(
    COUNTROWS(FILTER('Customers', 'Customers'[Status] = "Churned")),
    COUNTROWS('Customers'),
    0
) * 100

-- Monthly Recurring Revenue (MRR)
MRR = 
SUMX(
    FILTER('Subscriptions', 'Subscriptions'[Status] = "Active"),
    'Subscriptions'[Monthly_Price]
)

-- MRR Lost to Churn
MRR Lost = 
SUMX(
    FILTER('Subscriptions', 'Subscriptions'[Status] = "Churned"),
    'Subscriptions'[Monthly_Price]
)

-- Retention Rate %
Retention Rate % = 100 - [Churn Rate %]
```

---

## 💡 Key Insights (What I Found)

- 🔴 **Basic plan** had 3x higher churn than Pro and Enterprise plans — price-sensitive customers leave fastest
- 🏭 **Startup segment** churned at 42% — budget constraints were the primary driver
- 📣 **Paid acquisition channels** retained customers 2x longer than organic/free channels
- 💸 **MRR lost to churn** peaked in Q1 — post-holiday budget cuts drove cancellations
- ✅ **Annual plan customers** had 78% lower churn than monthly plan customers

---

## 📂 Repository Structure

```
Saas-Churn-Analysis/
│
├── dashboard/
│   └── saas_churn_dashboard.pbix
│
├── data/
│   └── saas_subscriptions.xlsx
│
└── README.md
```

---

## 🚀 How to Run This Project

1. Clone this repository
2. Open `saas_subscriptions.xlsx` to explore the raw data
3. Open `saas_churn_dashboard.pbix` in Power BI Desktop
4. Refresh the data connection if prompted

---

## 👤 Author

**Subhankar Das** — Aspiring Data Analyst from Kolkata, India

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR-LINK)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/subhankar-das18)
