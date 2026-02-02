# 🛵 Swiggy Sales Data Analysis Project

## 📌 Project Overview
This project involves a comprehensive analysis of Swiggy's food delivery data to derive actionable business insights. Using **SQL (T-SQL)**, the raw dataset was cleaned, transformed into a structured **Star Schema**, and analyzed to track key performance indicators (KPIs) such as revenue growth, customer spending behavior, and restaurant performance.

This project demonstrates the transition from raw, unstructured data to an optimized data model suitable for high-performance analytics.

## 📂 Business Requirements & Problem Statement
The primary objective was to ensure data integrity and build a scalable foundation for reporting. The project workflow was guided by the following business requirements:

1.  [cite_start]**Data Quality Audit:** Identify and handle missing values (NULLs) and inconsistencies in critical fields like `Order_Date`, `City`, and `Price_INR`[cite: 6, 7].
2.  [cite_start]**Duplicate Removal:** Detect duplicate records to prevent skewed analysis and ensure unique order integrity[cite: 20, 21].
3.  [cite_start]**Dimensional Modeling:** Transform the flat file into a **Star Schema** to separate descriptive attributes (Dimensions) from measurable metrics (Facts) for optimized query performance[cite: 24, 26].
4.  [cite_start]**KPI Development:** Generate insights on Revenue, Order Volume, Average Rating, and Delivery Trends[cite: 41].

## 🛠️ Tech Stack
* **Database:** Microsoft SQL Server (T-SQL)
* **Concepts:** Data Cleaning, Window Functions (CTE, ROW_NUMBER), Dimensional Modeling, Aggregations.
* **Domain:** Food Tech / E-commerce Analytics.

## ⚙️ Key Phases & Methodology

### 1. Data Cleaning & Validation
Before analysis, the raw data underwent rigorous cleaning to ensure accuracy:
* [cite_start]**Null Checks:** Validated columns like `state`, `city`, and `rating` to ensure no critical data was missing[cite: 7].
* [cite_start]**Standardization:** Identified and handled blank/empty strings[cite: 18].
* [cite_start]**De-Duplication:** Used `ROW_NUMBER()` within a Common Table Expression (CTE) to remove duplicate transaction rows while retaining the original records[cite: 23].

### 2. Data Modeling (Star Schema)
[cite_start]To improve query performance and organize the data logically, I implemented a Star Schema architecture[cite: 40]:

* **Fact Table:**
    * [cite_start]`fact_swiggy_orders`: Contains quantitative data (Price, Rating, Foreign Keys)[cite: 38].
* **Dimension Tables:**
    * [cite_start]`dim_date`: Detailed timeline (Year, Month, Quarter, Week)[cite: 32].
    * [cite_start]`dim_location`: Geographic hierarchy (State, City, Area)[cite: 33].
    * [cite_start]`dim_restaurant`: Restaurant details[cite: 34].
    * [cite_start]`dim_category`: Cuisine types[cite: 35].
    * [cite_start]`dim_dish`: Item details[cite: 36].

*(Note: Refer to the logical diagram in the project documentation)*

### 3. Business Analysis & Insights
SQL queries were written to extract the following insights:

* **📈 Sales Performance:**
    * [cite_start]Calculated Total Revenue (INR Million) and Total Orders[cite: 44, 45].
    * [cite_start]Analyzed Average Dish Price and Average Ratings[cite: 46, 47].

* **🗓️ Temporal Trends:**
    * [cite_start]**Monthly & Quarterly Growth:** Tracked order volume fluctuations over time[cite: 50, 51].
    * [cite_start]**Peak Days:** Identified the busiest days of the week for delivery[cite: 53].

* **📍 Geographic & Restaurant Analysis:**
    * [cite_start]identified Top 10 Cities by order volume[cite: 55].
    * [cite_start]Ranked Top 10 Restaurants and most popular Cuisines (Indian, Chinese, etc.)[cite: 58, 59].

* **💰 Customer Spending Habits:**
    * [cite_start]Segmented customers into spending buckets (e.g., `<100 INR`, `100-199 INR`, `500+ INR`) to understand the price sensitivity of the user base [cite: 63-68].

## 🧠 Key Learnings
* **Data Integrity:** Learned the importance of rigorous duplicate checks using Window Functions before performing any aggregations.
* [cite_start]**Schema Design:** Understood how normalizing data into Dimensions and Facts reduces redundancy and speeds up reporting compared to working with flat files[cite: 27, 28].
* **Business Logic:** Translated raw requirements into SQL logic to solve specific business questions regarding revenue and customer behavior.

## 🚀 Future Scope
* Connect this SQL database to **Power BI/Tableau** for visual dashboarding.
* Implement more complex analytics like Customer Retention Rate or Week-over-Week growth.

---
*This project is part of my portfolio demonstrating proficiency in SQL and Data Analytics.*
