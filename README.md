
# Walmart Sales Data Analysis

This project provides a complete analysis of Walmart sales data using SQL for data cleaning and transformation and Power BI for KPI reporting and visual dashboards.

## Project Overview
This project analyzes Walmart’s sales performance across multiple branches and product categories. It includes:

- Data cleaning and transformation using MySQL  
- Exploratory data analysis  
- KPI generation (Revenue, COGS, Gross Income, Ratings, Customer Behavior)  
- Power BI dashboard for visualization and insights  

## Objectives:
- Identify sales trends  
- Understand customer purchase behavior  
- Analyze branch-level performance  
- Evaluate profitable product lines  
- Build an interactive dashboard for business consumers  

## Dataset Description
The dataset used in this project originates from the [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting). It contains detailed transactional records from three Walmart branches located in Mandalay, Yangon, and Naypyitaw.

**File:** `WalmartSalesData.csv`  
**Rows:** 1000  
**Columns:** 17  

| Column | Description | Data Type      |
|--------|-------------| -------------- |
| Invoice ID | Unique transaction number | VARCHAR(30)    |
| Branch | A, B, or C | VARCHAR(5)    |
| City | City of the branch | VARCHAR(30)    |
| Customer type | Member or Normal | VARCHAR(30)    |
| Gender | Male / Female | VARCHAR(30)    |
| Product line | Category of item | FLOAT    |
| Unit price | Price per unit | DECIMAL(10, 2)     |
| Quantity | Units purchased | INT    |
| Tax 5% | Calculated 5% tax | FLOAT    |
| Total | Total billed amount | DECIMAL(12, 4)    |
| Date | Transaction date | DATETIME    |
| Time | Transaction time | TIME    |
| Payment | Payment method | VARCHAR(15)   |
| COGS | Cost of goods sold | DECIMAL(10, 2)    |
| Gross margin % | Margin percentage | FLOAT    |
| Gross income | Profit amount | DECIMAL(12, 4)    |
| Rating | Customer rating | FLOAT    |
  

## Data Cleaning & Transformation (SQL)
**SQL File:** `Walmart_sales_sql.sql`

### Tasks Performed
> 1. Created database and table  
> 2. Imported raw CSV data  
> 3. Applied correct data types  
> 4. Converted date and time fields  
> 5. Generated KPIs  
> 6. Performed aggregations and grouping  

### Example SQL Queries

**Total Revenue**
```sql
SELECT SUM(total) AS total_revenue FROM walmartSales;
```

**Sales by Branch**
```sql
SELECT branch, SUM(total) AS total_sales
FROM walmartSales
GROUP BY branch;
```

**Top Product Lines**
```sql
SELECT product_line, SUM(total) AS revenue
FROM walmartSales
GROUP BY product_line
ORDER BY revenue DESC;
```


## Business Questions Answered

### 🔹 **1. Sales Patterns**
> - Which branch generates the highest revenue?  
> - What are hourly and daily sales patterns?  
> - Which months show peak sales?

### 🔹 **2. Customer Insights**
> - Which customer types contribute the most revenue?  
> - Gender-based purchasing patterns  
> - Ratings comparison across branches

### 🔹 **3. Product Analysis**
> - Most profitable product lines  
> - Most frequently purchased categories  
> - COGS, gross income & VAT contribution

### 🔹 **4. Branch Performance**
> - Which branch performs the best overall?  
> - KPI comparison across Mandalay, Yangon, Naypyitaw

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

### Insights 
> - Food & Beverages is the top-performing product line, followed by Sports & Travel and Electronic Accessories.  
> - Branch B consistently generates the highest revenue.  
> - January is the highest-selling month, Saturday is the strongest day, and 7 PM is the peak sales hour.  
> - Female customers contribute slightly more revenue than males, and E-Wallet/Cash are the most preferred payment methods.    

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

This project showcases a complete end-to-end data analysis workflow, beginning with SQL-based data preparation and culminating in a fully interactive Power BI dashboard.

Through this analysis, we uncover valuable insights including:
- High-performing branches
- Top revenue-generating product lines
- Customer purchasing behavior
- Peak sales times
- Profitability trends

These insights can support data-driven decisions related to sales strategy, customer engagement, and product performance optimization.

---

## ⭐ Show Support  
If you like this project, consider giving it a ⭐ on GitHub!

