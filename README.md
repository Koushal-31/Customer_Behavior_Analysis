# Customer Shopping Behavior Analysis (Python • MySQL • Power BI)

An end-to-end data analytics project examining **3,900 retail customer transactions** across product categories, demographics, subscription tiers, and discount usage. The pipeline covers raw data cleaning in Python, relational querying in MySQL, and interactive KPI reporting in Power BI.

---

## Tech Stack
* Data Cleaning & ETL:** Python (Pandas, SQLAlchemy, PyMySQL / MySQL Connector)
* Database & Business Analysis:** MySQL 8+ (CTEs, Window Functions, Aggregations)
* Data Visualization & BI:** Power BI Desktop (ODBC Live Connection, Interactive Slicers, KPI Cards)

---

## Project Architecture & Workflow

1. Data Cleaning & Feature Engineering (Python):**
   * Handled missing values in `review_rating` using category-level median imputation.
   * Standardized column naming conventions (`snake_case`) and removed redundant fields (`promo_code_used`).
   * Engineered customer segmentation features including `age_group` (Young Adult, Adult, Middle-aged, Senior) and `purchase_frequency_days`.
   * Loaded the cleaned dataset directly into a local MySQL database (`customer_behavior.customer`).

2. Exploratory Business Analysis (MySQL):**
   * Executed 10 structured SQL queries answering core stakeholder questions:
     * Revenue breakdown by gender, age group, and product category.
     * Subscription status impact on average spend and repeat-buyer conversion (`> 5` previous purchases).
     * Top-performing products per category using `ROW_NUMBER()` window functions.
     * Discount dependency rates across items and shipping type comparisons (Standard vs. Express).

3. Interactive Dashboarding (Power BI):**
   * Connected Power BI directly to MySQL via `MySQL ODBC 26.10 Unicode Driver`.
   * Built executive KPI cards tracking **Number of Customers (3.9K)**, **Average Purchase Amount ($59.76)**, and **Average Review Rating (3.75)**.
   * Visualized **Revenue by Category**, **Sales Volume by Category**, and **Subscription Split (27% Yes / 73% No)** with dynamic filtering across **Subscription Status**, **Gender**, **Category**, and **Shipping Type**.

---

## Key Business Insights
* **Revenue & Volume Leaders:** Clothing generates the highest total revenue and unit sales volume, followed by Accessories, Footwear, and Outerwear.
* **Demographic Performance:** Young Adults contribute the largest share of total revenue ($62,143), followed by Middle-aged ($59,197), Adult ($55,978), and Senior ($55,763) segments.
* **Subscription Opportunity:** Only **27%** of customers are currently subscribed, leaving a major retention opportunity among repeat buyers.

---

## Repository Structure
```text
├── customer_shopping_behavior.csv            # Raw dataset (3,900 records)
├── customer_shopping_behavior_cleaning.ipynb # Python ETL & MySQL ingestion script
├── customer_behavior_analysis.sql            # 10 business SQL queries
├── customer_behavior_dashboard.pbix          # Interactive Power BI report
└── README.md                                 # Project documentation
