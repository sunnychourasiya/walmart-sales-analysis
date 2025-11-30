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
| Problem Statement | [Go to Section](#-problem-statement) |
| Project Objectives | [Go to Section](#-project-objectives) |
| Key Business Questions | [Go to Section](#-key-business-questions) |
| Project Workflow | [Go to Section](#-project-workflow) |
| Dataset Description | [Go to Section](#-dataset-description) |
| Data Cleaning & Transformation (MySQL) | [Go to Section](#-data-cleaning--transformation-mysql) |
| Business Intelligence (Power BI) | [Go to Section](#-business-intelligence-power-bi) |
| Key KPIs & DAX Measures | [Go to Section](#-key-dax-measures) |
| Key Insights  | [Go to Section](#-key-insights--business-impact) |
| Business Impact  | [Go to Section](#-business-impact) |
| Technologies Used | [Go to Section](#-technologies-used) |
| Dashboard Previews | [Go to Section](#-dashboard-previews) |
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

## ❓ Key Business Questions

### Revenue & Sales Performance
- Which branch generates the highest revenue and profit?
- Which product lines contribute most to profitability?
- How do revenue trends vary by hour, day, and month?

### Customer Insights
- Do Members spend more than Normal customers?
- How do gender-based purchasing patterns differ?
- Which categories receive the highest customer ratings?

### Product Profitability
- Which product lines produce the highest gross income?
- Is there a relationship between customer ratings and purchase volume?

### Branch Comparison
- Which branch demonstrates the strongest operational performance?
- How do satisfaction ratings vary across locations?

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

**SQL Script:** `supermarket_sales.sql`

This stage prepared the raw CSV data for analysis by applying a structured, repeatable data-engineering workflow.

### ✔ Key Activities Performed
- **Designed a relational schema and staging environment** to ensure consistent ingestion and validation of source data.
- **Standardized all data types** (e.g., DATE, TIME, DECIMAL) and corrected formatting inconsistencies to eliminate downstream reporting issues.
- **Engineered analytical time fields** using SQL functions:
  - `MONTHNAME(Date)`
  - `DAYNAME(Date)`
  - `HOUR(Time)`
- **Computed core KPIs** including Revenue, COGS, Tax, Gross Income, and Margin %, forming the foundation of the BI model.
- **Created aggregated views** for branch, product line, and customer-level analytics to optimize Power BI performance and simplify DAX logic.

This transformation layer ensures that all insights and dashboards are built on clean, reliable, analysis-ready data.


### Example SQL Queries

**Total Revenue**
```sql
SELECT SUM(total) AS total_revenue FROM Supermarket_Sales;
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


## 📊 Power BI Dashboard

**File:** `Supermarket_Sales_Analysis.pbix`

The dashboard serves as the primary decision-support interface, enabling business users to explore revenue, customer behavior, and product performance across three branches. It is built on a star-schema model with DAX-driven KPIs and interactive drilldowns.

### ✔ Key KPIs Presented
- **Total Revenue**
- **Gross Income**
- **Gross Margin %**
- **Total Quantity Sold**
- **Average Customer Rating**

These KPIs provide an immediate snapshot of overall commercial performance.

## KPI Examples

**Total Revenue**
```KPI
Total Revenue = SUM(supermarket_sales[Total])
```

**Average Customer Rating**
```KPI
Average Rating = AVERAGE(supermarket_sales[Rating])
```

### ✔ Core Dashboard Modules
- **Revenue Trends (Month & Day)**  
  Identifies seasonality and behavioural patterns in purchasing activity.

- **Branch Performance Overview**  
  Compares revenue, gross income, and transaction volume across Mandalay, Yangon, and Naypyitaw.

- **Category & Product Line Profitability**  
  Highlights top-performing and underperforming product categories.

- **Customer Insights (Gender & Customer Type)**  
  Breaks down spending patterns, ratings, and contribution by segment.

- **Payment Method Distribution**  
  Reveals customer payment preferences across branches.

- **Hourly & Daily Sales Patterns**  
  Pinpoints peak shopping windows to support operations and staffing decisions.

The multi-page dashboard enables drilldown from branch → product line → customer segment, providing a high-utility analytical experience for retail decision-makers.


## 🧮 DAX Example

```DAX

Revenue MoM % Change =
DIVIDE(
    [Total Revenue] -
        CALCULATE(
            [Total Revenue],
            DATEADD(Date[Date], -1, MONTH)
        ),
    CALCULATE(
        [Total Revenue],
        DATEADD(Date[Date], -1, MONTH)
    )
)

```

---

## 🧠 Key Insights 

### 📌 Revenue & Profitability
- **Electronics, Food & Beverages, and Home & Lifestyle** are the primary revenue and profit contributors, indicating strong customer demand and healthy category economics.
- **Branch B** consistently leads across total revenue, gross income, and margin performance, positioning it as the operational benchmark for the network.
- Stable **gross margin levels** across categories suggest effective pricing strategy and cost management.

### 📌 Customer Behavior
- **Female customers** contribute marginally higher revenue, reflecting distinct purchase patterns that can be leveraged for targeted campaigns.
- **Member customers** exhibit higher average transaction value compared to Normal customers, reinforcing the value of loyalty initiatives.
- **Customer satisfaction (ratings)** remains strong across all branches, supporting a positive service experience.

### 📌 Time-Based Performance
- Sales peak between **5 PM and 8 PM**, reflecting post-work shopping behavior and highlighting optimal staffing windows.
- **Saturday** records the highest footfall and revenue, suggesting strong weekend-driven demand.
- **January** emerges as the best-performing month, likely influenced by seasonal or post-holiday shopping trends.

---

### ⭐ Business Impact
The insights directly support improvements in:

- **Staffing Efficiency:** Align headcount with hourly demand peaks.  
- **Inventory Optimization:** Allocate fast-moving products to high-traffic periods and locations.  
- **Promotional Strategy:** Target profitable segments (Members, Female customers) and high-margin categories.  
- **Category Management:** Prioritize top-performing product lines to drive revenue growth.  
- **Customer Targeting:** Leverage segment behaviors to tailor offers and loyalty programs.

Overall, the analysis strengthens decision-making across operations, merchandising, marketing, and customer engagement.

---

## 🧰 Technologies Used

A modern, scalable analytics stack combining relational data processing with interactive BI reporting:

- **MySQL** — Data cleaning, transformation, KPI calculations, and aggregation logic  
- **SQL** — Joins, CTEs, date/time functions, and analytical queries  
- **Power BI** — Semantic data modeling, DAX measures, multi-page dashboards  
- **DAX** — KPI development, time-intelligence calculations, and business logic  
- **CSV/Excel** — Source data formats for ingestion and preprocessing  


---

## 🖼 Dashboard Previews

Below are snapshots from the 4-page Power BI dashboard delivered as part of this project.

### **1️⃣ Sales Overview Dashboard**
Provides a consolidated view of revenue, gross income, branch performance, and top-level KPIs.  
<img src="Images/Sales_Overview.png" width="550"/>

### **2️⃣ Product Performance Dashboard**
Highlights category-wise profitability, revenue contribution, and product line insights.  
<img src="Images/Product_Performance.png" width="550"/>

### **3️⃣ Customer Insights Dashboard**
Analyzes spending behavior, customer segments, ratings, and demographic trends.  
<img src="Images/Customer_Insights.png" width="550"/>

### **4️⃣ Time-Based Insights Dashboard**
Visualizes hourly, daily, and monthly demand patterns to support staffing and inventory decisions.  
<img src="Images/Time_Insights.png" width="550"/>
 

---

## 🏁 Conclusion

This project demonstrates a complete **retail analytics pipeline**, integrating SQL-based data engineering with Power BI visualization.  
The insights support improved **sales strategy**, **product assortment**, **operational efficiency**, and **customer engagement** — mirroring BI workflows used in modern retail organizations.

---

## ⭐ Show Support

If you found this project insightful, consider giving it a ⭐ on GitHub.

