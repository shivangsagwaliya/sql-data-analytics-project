

# SQL Data Analytics Project

![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-4285F4?style=for-the-badge&logo=google-analytics&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

##  Project Overview
A comprehensive collection of SQL scripts for data exploration, analytics, and reporting. These scripts cover various analyses such as database exploration, measures and metrics, time-based trends, cumulative analytics, segmentation, and more. This repository contains SQL queries designed to help data analysts and BI professionals quickly explore, segment, and analyze data within a relational database. Each script focuses on a specific analytical theme and demonstrates best practices for SQL queries.

The project is structured to help analysts quickly implement complex logic such as **Customer Segmentation**, **Time-Series Analysis**, and **Cumulative Metrics** without reinventing the wheel.

---

## 🎯 Key Features & Analysis Types

### 1. 📈 Time-Based Analysis
* **Month-over-Month (MoM) Growth:** Scripts to calculate percentage growth compared to the previous period using `LAG()` and Window Functions.
* **Moving Averages:** 3-month and 6-month rolling averages to smooth out volatility in sales data.
* **Year-over-Year (YoY) Comparison:** Comparing performance of the current month against the same month in the previous year.

### 2. 👥 Customer Segmentation
* **RFM Analysis (Recency, Frequency, Monetary):** Categorizing customers based on their purchasing behavior to identify "High Value" vs. "At Risk" customers.
* **Customer Lifetime Value (CLV):** Estimating the total revenue attribution of a customer over their entire relationship with the business.
* **New vs. Returning Customers:** Logic to distinguish between first-time buyers and repeat purchasers in any given period.

### 3. 📊 Advanced Aggregations
* **Cumulative Totals (Running Totals):** Calculating year-to-date (YTD) sales using `SUM() OVER(ORDER BY...)`.
* **Pareto Analysis (80/20 Rule):** Identifying the top 20% of products or customers that drive 80% of revenue.
* **Ranking & Top N:** Dynamic ranking of products by category using `RANK()` and `DENSE_RANK()`.

---

## 📂 Repository Structure

```text
sql-data-analytics-project/
│
├── datasets/              # Sample CSV files used for the SQL scripts
│   ├── sales_data.csv
│   └── customer_data.csv
│
├── scripts/               # SQL Scripts organized by analytical theme
│   ├── 01_time_series_analysis.sql    # MoM, YoY, Moving Averages
│   ├── 02_customer_segmentation.sql   # RFM, Churn Analysis
│   ├── 03_cumulative_metrics.sql      # Running Totals, YTD
│   └── 04_advanced_ranking.sql        # Pareto, Top N per Group
│
├── LICENSE
└── README.md
🛠️ Technical Concepts Demonstrated
This project showcases proficiency in the following SQL capabilities:

Window Functions: OVER(), PARTITION BY, ORDER BY, ROWS BETWEEN.

Common Table Expressions (CTEs): Using WITH clauses for cleaner, modular code.

Data Aggregation: Advanced GROUP BY logic and CASE statements for conditional aggregation.

Joins & Unions: Handling complex multi-table relationships.

Data Cleaning: Handling NULL values and casting data types for accurate calculation.

🚀 How to Use This Repository
Clone the Repo:

Bash

git clone [https://github.com/shivangsagwaliya/sql-data-analytics-project.git](https://github.com/shivangsagwaliya/sql-data-analytics-project.git)
Load Data: Import the sample CSVs from the datasets/ folder into your SQL database (SQL Server, PostgreSQL, or MySQL).

Run Scripts: Open any script in the scripts/ folder and execute it against your database tables. Note: You may need to adjust table names to match your schema.

💡 Example: Moving Average Query
A snippet of the code found in 01_time_series_analysis.sql

SQL

SELECT 
    OrderDate,
    TotalSales,
    AVG(TotalSales) OVER (
        ORDER BY OrderDate
        ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
    ) AS Three_Month_Moving_Avg
FROM Monthly_Sales;
