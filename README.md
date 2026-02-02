# 🛵 Swiggy Sales Data Analysis Project

## 📌 Project Overview
This project involves a comprehensive analysis of Swiggy's food delivery data to derive actionable business insights. Using **SQL (T-SQL)**, the raw dataset was cleaned, transformed into a structured **Star Schema**, and analyzed to track key performance indicators (KPIs) such as revenue growth, customer spending behavior, and restaurant performance.

This project demonstrates the transition from raw, unstructured data to an optimized data model suitable for high-performance analytics.

## 📂 Business Requirements & Problem Statement
The primary objective was to ensure data integrity and build a scalable foundation for reporting. The project workflow was guided by the following business requirements:

1.  **Data Quality Audit:** Identify and handle missing values (NULLs) and inconsistencies in critical fields like `Order_Date`, `City`, and `Price_INR`.
2.  **Duplicate Removal:** Detect duplicate records to prevent skewed analysis and ensure unique order integrity.
3.  **Dimensional Modeling:** Transform the flat file into a **Star Schema** to separate descriptive attributes (Dimensions) from measurable metrics (Facts) for optimized query performance.
4.  **KPI Development:** Generate insights on Revenue, Order Volume, Average Rating, and Delivery Trends.

## 🛠️ Tech Stack
* **Database:** Microsoft SQL Server (T-SQL)
* **Concepts:** Data Cleaning, Window Functions (CTE, ROW_NUMBER), Dimensional Modeling, Aggregations.
* **Domain:** Food Tech / E-commerce Analytics.

## ⚙️ Key Phases & Methodology

### 1. Data Cleaning & Validation
Before analysis, the raw data underwent rigorous cleaning to ensure accuracy:
* **Null Checks:** Validated columns like `state`, `city`, and `rating` to ensure no critical data was missing.
* **Standardization:** Identified and handled blank/empty strings.
* **De-Duplication:** Used `ROW_NUMBER()` within a Common Table Expression (CTE) to remove duplicate transaction rows while retaining the original records.

### 2. Data Modeling (Star Schema)
To improve query performance and organize the data logically, I implemented a Star Schema architecture:

* **Fact Table:**
    * `fact_swiggy_orders`: Contains quantitative data (Price, Rating, Foreign Keys).
* **Dimension Tables:**
    * `dim_date`: Detailed timeline (Year, Month, Quarter, Week).
    * `dim_location`: Geographic hierarchy (State, City, Area).
    * `dim_restaurant`: Restaurant details.
    * `dim_category`: Cuisine types.
    * `dim_dish`: Item details.

*(Note: Refer to the logical diagram in the project documentation)*

### 3. Business Analysis & Insights
SQL queries were written to extract the following insights:

* **📈 Sales Performance:**
    * Calculated Total Revenue (INR Million) and Total Orders.
    * Analyzed Average Dish Price and Average Ratings.

* **🗓️ Temporal Trends:**
    * **Monthly & Quarterly Growth:** Tracked order volume fluctuations over time.
    * **Peak Days:** Identified the busiest days of the week for delivery.

* **📍 Geographic & Restaurant Analysis:**
    * Identified Top 10 Cities by order volume.
    * Ranked Top 10 Restaurants and most popular Cuisines (Indian, Chinese, etc.).

* **💰 Customer Spending Habits:**
    * Segmented customers into spending buckets (e.g., `<100 INR`, `100-199 INR`, `500+ INR`) to understand the price sensitivity of the user base.

## 🧠 Key Learnings
* **Data Integrity:** Learned the importance of rigorous duplicate checks using Window Functions before performing any aggregations.
* **Schema Design:** Understood how normalizing data into Dimensions and Facts reduces redundancy and speeds up reporting compared to working with flat files.
* **Business Logic:** Translated raw requirements into SQL logic to solve specific business questions regarding revenue and customer behavior.
---
*This project is part of my portfolio demonstrating proficiency in SQL and Data Analytics.*
