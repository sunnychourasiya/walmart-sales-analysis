# 📊 Supermarket Sales Data Analysis

A Complete Retail Analytics Project Using MySQL & Power BI

Built an end-to-end retail analytics pipeline using MySQL + Power BI, transforming raw supermarket sales data into actionable insights on revenue, profit, customer behavior, product performance, and time-based sales trends across three branches.

---

## 📘 Executive Summary

This project presents an end-to-end **Supermarket Sales Analytics** solution using **MySQL** for data engineering and **Power BI** for interactive business intelligence reporting.

Using **1,000 point-of-sale transactions** from three supermarket branches, the project uncovers insights across:

- **Revenue & profitability**
- **Customer purchasing behavior**
- **Product category performance**
- **Time-based sales trends**

The goal is to support supermarket decision-making across **store operations**, **category management**, **customer behavior analysis**, and **marketing optimization**.  
The workflow replicates a **real-world retail BI pipeline**, including data cleaning, KPI modeling, dashboard creation, and insight generation.

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

## 🔍 Project Overview

Retail managers require real-time visibility into:

- Branch sales performance
- Revenue and profitability
- Customer behavior differences
- Product category trends
- Peak sales hours and demand patterns

This project transforms raw CSV data into analysis-ready tables, builds a star-schema BI model, and develops Power BI dashboards to solve these challenges.

---

## 🎯 Project Objectives

### 1. Revenue & Profitability
- Identify top-performing product categories  
- Compare revenue and profit across branches  
- Analyze gross income and margin patterns  

### 2. Customer Behavior
- Compare spending patterns (Member vs Normal customers)  
- Analyze gender-based revenue contribution  
- Evaluate satisfaction through customer ratings  

### 3. Product & Category Analytics
- Identify profitable and fast-moving product lines  
- Explore relationships between ratings and sales  

### 4. Time-Based Trends
- Identify peak shopping hours and high-traffic days  
- Study revenue patterns across days and months  

---

## 📂 Dataset Description

This project uses the **Supermarket Sales Dataset** from Kaggle containing 1,000 transaction-level records.

**Dataset:** https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales     
**File:** `supermarket_sales_data.csv`  
**Rows:** 1,000 | **Columns:** 17  
 
### Key Features  
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

## Project Structure
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

