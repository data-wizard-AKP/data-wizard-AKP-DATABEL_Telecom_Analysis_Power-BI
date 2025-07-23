## 📘 Project Overview

This project delves into a simulated dataset from **Databel**, a fictional telecommunications company, to analyze and predict customer churn. Customer churn—the rate at which customers stop doing business with a company—presents a significant challenge for telecom providers, directly impacting revenue and growth.

This analysis aims to:

- 🔍 **Identify Key Drivers of Customer Churn**  
  Uncover the primary factors influencing customer attrition across demographics, usage patterns, and billing behaviors.

- 🧠 **Build Predictive Awareness**  
  While this report is descriptive, it lays the foundation for future predictive models capable of identifying high-risk churn customers before they leave.

- 💡 **Generate Actionable Insights**  
  Provide data-driven recommendations for targeted customer retention strategies based on churn trends and segment behavior.

---

## ❗ Problem Statement

Telecom companies face high churn rates, especially among month-to-month subscribers, younger users, and customers incurring extra charges. Understanding the root causes of churn is essential for designing effective retention strategies.

**Key Questions Addressed:**
- Which customer segments are most likely to churn?
- How do contract types, payment methods, and usage patterns influence churn?
- What actionable steps can reduce churn and improve customer loyalty?

---

## 📦 Dataset Overview

- **Total Records Analyzed**: 6,687 customer entries  
- **Data Includes**:  
  - Demographics (age, gender, tenure)  
  - Subscription details (plan type, contract duration)  
  - Usage metrics (international calls, service usage)  
  - Billing information (monthly charges, extra fees)  
  - Churn indicator (Yes/No)

The dataset provides a rich foundation for understanding churn behavior across multiple dimensions.

---

## 🧩 Data Model

The Power BI report is built on a star schema with clearly defined dimension and fact tables:

| Table Name             | Type       | Description                                                          |
|------------------------|------------|----------------------------------------------------------------------|
| `Customer`             | Dimension  | Contains customer attributes like ID, gender, age, tenure, contract  |
| `Geographic`           | Dimension  | Includes location-based data such as region, state, and city         |
| `UserRegionMapping`    | Dimension  | Maps Regional Managers to geographic regions for implementing RLS                |
| `Databel - Data`       | Fact       | Core transactional table with usage metrics, billing details, churn  |


⚡ **Note**: A leaner data model with fewer dimension tables improves dashboard performance and simplifies relationships, enabling faster load times and smoother interactivity.
### 📐 Data Model Diagram

<img width="1440" height="900" alt="Star schema data model showing Customer, Geographic, UserRegionMapping, and Databel - Data tables" src="https://github.com/user-attachments/assets/0d6a8930-be91-45d2-8f85-cf94d89955d5" />

This model ensures efficient filtering, slicing, and aggregation across multiple dimensions, enabling rich interactive analysis.

---

## 📁 Report Structure

The Power BI report is organized into 10 analytical sections:

1. **Overview** – Total churn and customer base  
2. **Churn Demographics** – Age, gender, tenure analysis  
3. **Groups and Categories** – Segment-wise churn  
4. **Unlimited Plan** – Plan type impact  
5. **International Calls** – Usage-based churn  
6. **Contract Type** – Duration vs. loyalty  
7. **Age Groups** – Age-wise churn trends  
8. **Payment and Contract** – Payment method influence  
9. **Extra Charges** – Billing-related churn  
10. **Insights** – Summary and recommendations

---

## 🔍 Key Findings

- 📉 **Month-to-Month Contracts** have the highest churn rate  
- 💸 **Extra Charges** significantly increase churn risk  
- 📶 **Unlimited Plan Users** are more loyal  
- 🌍 **International Callers** show elevated churn  
- 👥 **Young (18–25) and Senior (60+) Age Groups** are more likely to leave
- --
## 🔐 Security Features

- **Dynamic Row-Level Security (RLS)** is implemented using the `UserRegionMapping` table and the DAX function `USERPRINCIPALNAME()`.  
  This ensures that each **Regional Manager** accessing the report sees only the data relevant to their assigned geographic region—automatically filtered based on their login credentials.

### 🧠 How It Works

- The `UserRegionMapping` table contains mappings between user email addresses and their assigned regions.
- A DAX filter rule is applied to the `Geographic` or `Customer` table:
  ```DAX
  [Email] = USERPRINCIPALNAME()




---

## ✅ Recommendations

- Offer incentives to convert month-to-month users to long-term contracts  
- Provide clearer billing and dedicated international call packages  
- Encourage auto-pay enrollment to improve retention  
- Tailor engagement strategies for vulnerable age groups

---

## 🛠️ Tools & Technologies

- Power BI Desktop  
- DAX for calculated measures  
- Interactive visuals and slicers  
- CSV data source with 6,687 rows  
- Star schema data model for optimized performance

---
# 📊 Customer Churn Analysis – Power BI Report

🔗 **Live Interactive Report**  
[View the live Power BI report](https://app.powerbi.com/reportEmbed?reportId=b9487d77-09d3-454a-a374-41ba7158823c&autoAuth=true&ctid=8cb27e41-78c4-4e99-8761-8e71a6432b6a)


[View the Power BI report without login](https://github.com/data-wizard-AKP/data-wizard-AKP-DATABEL_Telecom_Analysis_Power-BI/blob/main/Customer_Churn_Anlysis.pptx)

---

## 👤 Author

**Arun** – Data Analyst  
Skilled in Power BI, Excel, and SQL  
Passionate about storytelling with data

---

Feel free to explore the `.pbix` file, interact with slicers, and dive into the insights. Contributions and feedback are welcome!
