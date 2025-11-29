# 📊 Walmart Sales Data Analysis  
*A Data-Driven Evaluation of Retail Performance, Customer Behavior & Product Profitability*

---

## 📘 Executive Summary  
This project presents a complete retail analytics workflow using **MySQL** for data preparation and **Power BI** for KPI reporting and visualization. The analysis reveals critical insights across branches, product categories, customer segments, and time periods. These insights support decision-making in pricing strategy, operational efficiency, customer engagement, and category management.

---

## 🔍 Project Overview  
The analysis focuses on evaluating Walmart’s sales performance across three geographic branches. By leveraging structured SQL transformations and a Power BI dashboard, this project identifies:

- High-performing product lines  
- Customer purchasing and rating patterns  
- Branch-level revenue and profitability differences  
- Time-based sales trends (daily, monthly, hourly)  

The end-to-end workflow includes:

- Data ingestion and validation  
- Cleaning and transformation using MySQL  
- Exploratory KPI analysis  
- Dashboard development for interactive insights  

---

## 🎯 Project Objectives  
- Measure and compare branch-level performance  
- Identify profitable and fast-moving product categories  
- Evaluate customer behavior across demographics and membership types  
- Analyze margin, gross income, and VAT contribution  
- Understand peak sales periods to optimize marketing & staffing  
- Provide an interactive BI dashboard for stakeholders  

--- 

## Dataset Description
The dataset used in this project originates from the [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting). It contains detailed transactional records from three Walmart branches located in Mandalay, Yangon, and Naypyitaw.

**File:** `WalmartSalesData.csv`  
**Rows:** 1000  
**Columns:** 17  

| Column | Description |
|--------|-------------|
| Invoice ID | Unique transaction code |
| Branch | A, B, or C |
| City | Location of the branch |
| Customer type | Member / Normal |
| Gender | Male / Female |
| Product line | Purchased product category |
| Unit price | Price per item |
| Quantity | Units bought |
| Tax 5% | VAT applied |
| Total | Final billed amount |
| Date | Purchase date |
| Time | Purchase time |
| Payment | Payment method |
| COGS | Cost of goods sold |
| Gross margin % | Margin percentage |
| Gross income | Profit generated |
| Rating | Customer satisfaction (1–10) |

---

## Data Cleaning & Transformation (SQL)
**SQL File:** `Walmart_sales_sql.sql`

### Tasks Performed  
- Created database and structured tables  
- Loaded and validated raw CSV data  
- Cleaned fields and standardized data types  
- Extracted date, time, and derived fields  
- Built analytical KPIs (Revenue, COGS, Gross Margin, Gross Income)  
- Performed aggregations for trend and category analysis


### Example SQL Queries

**Total Revenue**
```sql
SELECT SUM(total) AS total_revenue FROM walmartSales;
```

**Category-Level Profitability Ranking**
```sql
SELECT product_line,
       SUM(gross_income) AS total_profit
FROM walmartSales
GROUP BY product_line
ORDER BY total_profit DESC;
```

**Hourly Sales Trend**
```sql
SELECT HOUR(time) AS hour_of_day,
       SUM(total) AS revenue
FROM walmartSales
GROUP BY hour_of_day
ORDER BY hour_of_day;
```

---


## Business Questions Answered

### 🔹 1. Revenue & Sales Performance
- Which branch generates the highest revenue and profit?
- What are the strongest and weakest product categories?
- How do sales vary by month, day, and hour?

### 🔹 2. Customer Insights
- Which customer segment (Member/Normal) spends more?
- Do purchasing patterns vary by gender?
- How do customer ratings differ across product lines?

### 🔹 3. Product Profitability
- Which product lines have the highest margins?
- Are higher-rated products purchased more frequently?

### 🔹 4. Branch-Level Analysis
- Operational effectiveness across Mandalay, Yangon, and Naypyitaw
- Branch-level contribution to revenue, quantity sold, and gross income

---

## Power BI Dashboard
**File:** `Walmart_Sales_Analysis.pbix`

### KPIs
> - Total Revenue  
> - Total Quantity Sold  
> - Total Gross Income  
> - Average Customer Rating    

### Visuals
> - Monthly Revenue Trend  
> - Sales by Product Line  
> - Profit Trend Monthly  
> - Customer Ratings By Time  
> - Gender-based Purchase Comparison  
> - Payment Method Distribution   

---

## Project Structure
```
Walmart-Sales-Analysis/
│
├── data/
│   └── Walmart_Sales_Data.csv
│
├── sql/
│   └── Walmart_Sales.sql
│
├── dashboard/
│   └── Walmart_Sales.pbix
│
└── README.md
```

---

## Key Insights and Business Impact

### Revenue Insights
- Electronics, Food & Beverages, and Home & Lifestyle are the highest revenue-generating product lines.
- Branch B consistently records the strongest performance in total revenue.
- Customer ratings remain above average across all branches, reflecting strong satisfaction levels.

### Customer Behavior Patterns
- Female customers contribute slightly more to total sales than male customers.
- E-Wallet is the most preferred payment method, followed by Credit Card and Cash.
- Sales peak between **5 PM and 8 PM**, indicating strong evening shopping activity.

### Product and Category Insights
- Sports & Travel and Food & Beverages show strong performance in both revenue and customer ratings.
- Higher-rated product lines tend to correlate with higher quantities sold.

---

## Technologies Used

- **MySQL** – Data cleaning, transformation, and KPI generation
- **Power BI** – Dashboard creation, data modeling, and interactive visual analytics

---

## Dashboard Screenshots

<h3>Walmart Sales Overview</h3>
<img src="Images/Walmart_Sales_Overview.png" width="450">

<h3>Walmart Product Performance</h3>
<img src="Images/Walmart_Product_Performance.png" width="450">

<h3>Walmart Customer Insights</h3>
<img src="Images/Walmart_Customer_Insights.png" width="450">

<h3>Walmart Time Insights</h3>
<img src="Images/Walmart_Time_Insights.png" width="450">

---

## Conclusion

This project demonstrates a complete, real-world retail analytics pipeline—from structured SQL transformations to interactive Power BI dashboards. The insights derived help optimize product strategies, refine branch operations, and enable more targeted, data-driven decisions across marketing and customer experience functions.

---

## ⭐ Show Support  
If you like this project, consider giving it a ⭐ on GitHub!

