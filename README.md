# 📊 Supermarket Sales Data Analysis

A Complete Retail Analytics Project Using MySQL & Power BI

<p align="left">

  <img src="https://img.shields.io/badge/MySQL-Data%20Engineering-blue" />
  <img src="https://img.shields.io/badge/SQL-Transformations-lightgrey" />
  <img src="https://img.shields.io/badge/Power%20BI-Dashboarding-F2C811" />
  <img src="https://img.shields.io/badge/DAX-KPI%20Modeling-purple" />
  <img src="https://img.shields.io/badge/Excel%2FCSV-Source%20Data-green" />

</p>

---

## 📌 Project Summary

| **Category**     | **Details** |
|------------------|-------------|
| **Domain**       | Retail Sales Analytics |
| **Objective**    | Analyze revenue, customers, products, and time-based demand across 3 supermarket branches |
| **Dataset**      | 1,000 POS transactions × 17 fields |
| **Deliverables** | SQL-cleaned dataset, KPI model, DAX measures, 4-page Power BI dashboard |
| **Tech Stack**   | MySQL, SQL, Power BI, DAX, Excel/CSV |
| **Business Impact** | Better revenue insights, optimized inventory & staffing, improved category decisions & customer targeting |

---

## 📊 Key Highlights at a Glance

- Processed **1,000+** supermarket transactions  
- **Branch B** is the top performer in revenue & profit  
- **Electronics, Food & Beverages, Home & Lifestyle** drive most profit  
- **Members** spend more per transaction than Normal customers  
- **Females** contribute slightly higher revenue  
- Peak sales time: **5 PM – 8 PM**  
- Highest traffic day: **Saturday**  
- Best month: **January**  
- Delivered a complete **SQL → Power BI** analytics pipeline  

---

## Repository Structure
```
Supermarket-Sales-Analysis/
│
├── data/
│   └── supermarket_sales_data.csv
│
├── sql/
│   └── supermarket_sales.sql
│
├── dashboard/
│   └── Supermarket_Sales_Analysis.pbix
│
└── README.md
```

---


## 📘 Executive Overview

This project delivers a complete **Supermarket Sales Analytics solution** by combining **MySQL-based data engineering** with a **Power BI business intelligence layer**.  
Using **1,000 point-of-sale transactions** from branches in **Mandalay, Yangon, and Naypyitaw**, the solution provides a unified view of:

- **Revenue and gross profit performance**
- **Customer behavior by segment and gender**
- **Product category contribution and margin drivers**
- **Time-based demand patterns across hours, days, and months**

The output equips supermarket leaders with the insights needed to improve **sales strategy**, **category management**, **inventory planning**, and **customer engagement**.  
The workflow reflects a **real-world enterprise BI pipeline**, enabling repeatable, scalable analytics for retail decision-making.

--- 


## 📑 Table of Contents

| **Section** | **Link** |
|------------|----------|
| Executive Summary | [Go to Section](#-executive-summary) |
| Project Overview | [Go to Section](#-project-overview) |
| Project Objectives | [Go to Section](#-project-objectives) |
| Dataset Description | [Go to Section](#-dataset-description) |
| Data Engineering (MySQL) | [Go to Section](#-data-cleaning--transformation-mysql) |
| Business Intelligence (Power BI) | [Go to Section](#-business-intelligence-power-bi) |
| Business Questions Addressed | [Go to Section](#-business-questions-addressed) |
| Key KPIs & DAX Measures | [Go to Section](#-key-dax-measures) |
| Insights & Business Impact | [Go to Section](#-key-insights--business-impact) |
| Analytics Architecture | [Go to Section](#-analytics-architecture) |
| Project Structure | [Go to Section](#project-structure) |
| Technologies Used | [Go to Section](#-technologies-used) |
| Dashboard Previews | [Go to Section](#-dashboard-previews) |
| Future Enhancements | [Go to Section](#-future-enhancements) |
| Conclusion | [Go to Section](#-conclusion) |
| Show Support | [Go to Section](#-show-support) |

---

## 🔍 Problem Statement

Supermarket leadership lacked a consolidated analytics framework to answer essential business questions across branches, customers, products, and demand cycles.  
Key gaps included:

- No clear visibility into **branch-level revenue and profitability**
- Limited understanding of **Member vs Normal customer behavior**
- No structured view of **high-margin or fast-moving product categories**
- Insufficient insight into **peak sales hours, days, and monthly cycles**

These limitations affected **inventory decisions**, **staffing efficiency**, **promotional planning**, and **customer targeting**.  
This project addresses these challenges by building a complete SQL → Power BI pipeline that transforms raw transactional data into actionable insights.

---

## Project Objectives

- Identify the key revenue, customer, and product factors driving supermarket performance  
- Compare sales and profitability patterns across branches, customer segments, and product categories  
- Engineer analytical fields that enhance demand analysis, margin evaluation, and customer segmentation  
- Deliver actionable insights to support pricing, inventory planning, staffing, and category management teams  
- Establish a clean, scalable analytical foundation suitable for advanced forecasting and retail BI expansion  

---

## Project Workflow

```

Raw Data -→ MySQL Data Cleaning -→ KPI & Derived Fields -→ Power BI Data Model -→ DAX Measures -→ Interactive Dashboards -→ Insights -→ Business Recommendations

```

---

## 📂 Dataset Description

This project uses the **Supermarket Sales Dataset** from Kaggle containing 1,000 transaction-level records.

**Dataset:** [Supermarket Sales Data](https://www.kaggle.com/datasets/markmedhat/supermarket-sales)      
**File:** `supermarket_sales_data.csv`  
**Rows:** 1,000 | **Columns:** 17  
 
### Columns Overview  
| Column | Description |
|--------|-------------|
| Invoice ID | Unique transaction identifier |
| Branch | A, B, or C |
| City | Branch location |
| Customer type | Member / Normal |
| Gender | Male / Female |
| Product line | Category of product purchased |
| Unit price | Price per individual item |
| Quantity | Units purchased |
| Tax 5% | VAT applied |
| Total | Final billed amount |
| Date | Transaction date |
| Time | Transaction time |
| Payment | Payment method |
| COGS | Cost of goods sold |
| Gross margin % | Margin percentage |
| Gross income | Profit generated |
| Rating | Customer rating (1–10) | 

---

## 🛠 Data Cleaning & Transformation (MySQL)  
**SQL File:** `Supermarket_Sales.sql`

### Key Steps Performed

- Created database schema & staging environment
- Cleaned fields and standardized column types
- Derived time-based fields using SQL functions: 
  - `MONTHNAME(date)`  
  - `DAYNAME(date)`  
  - `HOUR(time)`  
- Calculated KPIs (Revenue, Tax, COGS, Gross Income, Margin %)
- Generated aggregated tables for Power BI modeling 

### Example SQL Queries

**Total Revenue**
```sql
SELECT SUM(total) AS total_revenue FROM Supermarket_Sales;
```

**Category-Level Profitability Ranking**
```sql
SELECT product_line,
       SUM(gross_income) AS total_profit
FROM Supermarket_Sales
GROUP BY product_line
ORDER BY total_profit DESC;
```

**Hourly Sales Trend**
```sql
SELECT HOUR(time) AS hour_of_day,
       SUM(total) AS revenue
FROM Supermarket_Sales
GROUP BY hour_of_day
ORDER BY hour_of_day;
```

---


## ❓ Business Questions Addressed

### **Revenue & Sales Performance**
- Which branch achieves the highest revenue and profit?  
- Which product lines are most profitable?  
- What are the hourly, daily, and monthly revenue trends?  

### **Customer Insights**
- Do Members spend more than Normal customers?  
- How do gender-based spending behaviors differ?  
- Which product lines receive the highest ratings?  

### **Product Profitability**
- Which categories generate the highest gross income?  
- Do higher-rated products sell more frequently?  

### **Branch Comparison**
- Which branch performs best operationally?  
- How do satisfaction ratings vary by location?  

---

## 📊 Power BI Dashboard

**Dashboard File:** `Supermarket_Sales_Analysis.pbix`

### **KPIs Displayed**
- Total Revenue  
- Gross Income  
- Gross Margin %  
- Total Quantity Sold  
- Average Customer Rating  

### **Key Dashboard Visuals**
- Revenue by Month & Day  
- Branch-Level Performance  
- Category & Product Line Revenue  
- Ratings Over Time  
- Gender-Based Spending  
- Payment Method Distribution  
- Hourly Revenue Patterns   

---

## 🧮 Key DAX Measures

```DAX
Total Revenue = SUM(supermarket_sales[Total])

Total Quantity = SUM(supermarket_sales[Quantity])

Gross Income = SUM(supermarket_sales[Gross income])

Gross Margin % = DIVIDE(
    [Gross Income],
    SUM(supermarket_sales[COGS])
)

Average Rating = AVERAGE(supermarket_sales[Rating])

Revenue MoM % Change =
DIVIDE(
    [Total Revenue] - CALCULATE([Total Revenue], DATEADD(Date[Date], -1, MONTH)),
    CALCULATE([Total Revenue], DATEADD(Date[Date], -1, MONTH))
)
```
---

## 🧠 Key Insights & Business Impact

### **Revenue & Profitability**
- Electronics, Food & Beverages, and Home & Lifestyle lead in revenue and profit.  
- Branch B demonstrates the strongest revenue and gross income performance.  
- High margins indicate an effective pricing and category strategy.  

### **Customer Behavior**
- Female customers contribute slightly higher overall revenue.  
- Member customers spend more per transaction than Normal customers.  
- Customer ratings remain consistently high across all branches.  

### **Time-Based Performance**
- Peak sales occur between **5 PM and 8 PM**.  
- **Saturdays** show the highest transaction volume.  
- **January** recorded the strongest month in terms of revenue.  

These insights help optimize **staffing**, **inventory planning**, **promotional strategies**, **category assortment**, and **customer targeting**.  

---

## 🧰 Technologies Used

- **MySQL** – Data cleaning, transformation, KPI modeling  
- **Power BI** – Data modeling, DAX, dashboards  
- **SQL** – Aggregations, joins, date/time functions  
- **DAX** – KPI design & analytical calculations  
- **CSV/Excel** – Source data format  

---

## 🖼 Dashboard Previews

### **1. Sales Overview Dashboard**
<img src="Images/Sales_Overview.png" width="550"/>

### **2. Product Performance Dashboard**
<img src="Images/Product_Performance.png" width="550"/>

### **3. Customer Insights Dashboard**
<img src="Images/Customer_Insights.png" width="550"/>

### **4. Time-Based Insights Dashboard**
<img src="Images/Time_Insights.png" width="550"/>

---

## 🧭 Future Enhancements

- Build forecasting models (Prophet / ARIMA)  
- Perform customer segmentation using clustering  
- Convert schema to star-schema dimensional modeling  
- Enable scheduled refresh via Power BI Gateway  
- Expand dataset for broader trend analysis  

---

## 🏁 Conclusion

This project demonstrates a complete **retail analytics pipeline**, integrating SQL-based data engineering with Power BI visualization.  
The insights support improved **sales strategy**, **product assortment**, **operational efficiency**, and **customer engagement** — mirroring BI workflows used in modern retail organizations.

---

## ⭐ Show Support

If you found this project insightful, consider giving it a ⭐ on GitHub.

