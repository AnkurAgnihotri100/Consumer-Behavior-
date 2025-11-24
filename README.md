# Customer Shopping Behavior Analysis


## Project Overview
This project analyzes customer purchase records to surface revenue drivers, customer segments, discount behavior, shipping impact, and top-performing products. The workflow includes data cleaning in Python, analytical SQL in MySQL 8+, and an interactive Power BI dashboard for visualization and stakeholder-ready insights.

---

## Dataset Summary
- ~3.9K transaction rows (customers, purchases, ratings, shipping, subscription status, previous purchases, category, item purchased, timestamps).  
- Key fields: `customer_id`, `purchase_amount`, `gender`, `age_group`, `item_purchased`, `review_rating`, `discount_applied`, `shipping_type`, `subscription_status`, `previous_purchases`, `purchase_date`.

## What I built
1. **Data cleaning & feature engineering** (Python / Pandas)  
   - Standardized column names, data types, date parsing  
   - Imputed missing review ratings using median rating by category  
   - Created `age_group`, `customer_segment` (New/Returning/Loyal), and `purchase_frequency_days`

2. **Analytical database** (MySQL 8+)  
   - Loaded cleaned data into MySQL  
   - Wrote analytical queries to answer 10 business questions (listed below)

3. **Interactive Power BI dashboard**  
   - KPI cards (Total revenue, Avg order value, Avg rating)  
   - Bar charts, line charts, matrix tables and slicers for interactive exploration  
   - Views for revenue by gender, age-group revenue, shipping comparison, subscription impact, top products

---

## How it works (pipeline)
1. **Data preparation (Python)**  
   - `data_cleaning.ipynb` (or `data_cleaning.py`) steps:
     - Load CSV
     - Remove duplicates & invalid rows
     - Impute missing ratings: `median(rating) by category`
     - Create `age_group`, `previous_purchases` bins
     - Export cleaned CSV: `customer_cleaned.csv`

2. **Load to MySQL (MySQL 8+)**  
   - Create schema and import `customer_cleaned.csv` using `LOAD DATA` or a database client.

3. **Run analytical SQL**  
   - Execute the queries in the `SQL Queries` section below (examples included).

4. **Visualize (Power BI)**  
   - Import the same cleaned CSV or connect Power BI to MySQL
   - Build visuals and publish .pbix or export to PDF (see provided PDF).

---
