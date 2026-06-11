# Customer Shopping Behavior Analysis 🛍️

An end-to-end data analytics project demonstrating data ingestion, exploratory analytics, relational database schema optimization, and executive business intelligence modeling.

## 🛠️ Tech Stack & Tools
* **Data Auditing:** Microsoft Excel
* **Exploratory Data Analysis (EDA):** Python (Jupyter Notebook, Pandas)
* **Database Management:** PostgreSQL
* **Data Visualization & BI:** Power BI

---

## 📐 Project Architecture & Pipeline
1. **Data Cleaning:** Profiled raw transactional files to verify data types and validate value constraints using Excel.
2. **Exploratory Analytics:** Used Python (Jupyter Notebook) to handle initial structural checks and outline categorical variables.
3. **Database Engineering:** Built a structured PostgreSQL data schema, populated the database, and ran complex analytical queries.
4. **BI Dashboarding:** Connected Power BI to the data views, engineered star-schema modeling pipelines, and generated interactive visual reports.

---

## 📊 Core Data Insights (Verified Metrics)
* **Total Cleaned Scope:** 3,900 unique transactional profiles
* **Gross Revenue Captured:** $233,081
* **Average Order Value (AOV):** $59.76
* **Average Customer Rating:** 3.75 / 5
* **Top Performance Categories:** * *Clothing:* $104,264 (1,737 units sold)
  * *Accessories:* $74,200 (1,240 units sold)
* **Demographic Concentration:** Male transactions account for 68% of the total dataset activity (2,652 entries).
* **Top Geographic Markets:** Montana ($5,784), Illinois ($5,617), and California ($5,605).

---

## 🗄️ SQL Database Implementation Example
```sql
-- Query executed to isolate category yields and user satisfaction rankings
SELECT category,
       COUNT(customer_id) AS total_transactions,
       SUM(purchase_amount_usd) AS gross_revenue,
       ROUND(AVG(purchase_amount_usd), 2) AS average_spend,
       ROUND(AVG(review_rating), 2) AS average_satisfaction_score
FROM retail_shopping_behavior
GROUP BY category
ORDER BY gross_revenue DESC;
