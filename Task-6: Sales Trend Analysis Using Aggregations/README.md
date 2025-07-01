Task - 6
# 📊 Sales Trend Analysis Using Aggregations

📅 Date: 01-07-2025  
📂 Task: Sales Trend Analysis Using Aggregations

## 🛠️ Tool Used: PostgreSQL (via pgAdmin)

## 📂 Dataset

- Dataset Name: `online_sales.csv`
- Source: [Online Sales Data](https://www.kaggle.com/datasets/shreyanshverma27/online-sales-dataset-popular-marketplace-data)
---

## 🎯 Objective
To analyze **monthly revenue** and **order volume** from an e-commerce dataset using SQL aggregations. The goal is to uncover sales patterns and trends over time, enabling data-driven business insights.

---

## 📦 Dataset Description

The dataset (`online_sales.csv`) contains the following relevant columns:

- `transaction_id`: Unique ID for each transaction  
- `date`: Order date (YYYY-MM-DD format)  
- `total_revenue`: Revenue generated from the transaction  
- `product_category`, `units_sold`, `region`, and more  

---

## 🧠 Approach & SQL Concepts Applied

This task uses SQL techniques such as:

- `EXTRACT(YEAR FROM date)` and `EXTRACT(MONTH FROM date)` to break down date values  
- `SUM(total_revenue)` to calculate total monthly revenue  
- `COUNT(DISTINCT transaction_id)` to measure order volume  
- `GROUP BY` and `ORDER BY` for structured aggregation and sorting  
- `WHERE ... BETWEEN` to limit analysis to the 2024 time period  

---

## 💻 SQL Script Used

```sql
SELECT
    EXTRACT(YEAR FROM date) AS year,
    EXTRACT(MONTH FROM date) AS month,
    SUM(total_revenue) AS monthly_revenue,
    COUNT(DISTINCT transaction_id) AS order_volume
FROM
    online_sales
WHERE
    date BETWEEN '2024-01-01' AND '2024-12-31'
GROUP BY
    year, month
ORDER BY
    year, month;
```

## 📈 Analysis Summary

- The results revealed clear monthly sales trends, highlighting both high and low-performing months.
- Peak revenue months were likely influenced by seasonal demand or promotions.
- Comparing revenue with order volume helped distinguish between more sales vs. higher-value transactions.
- This aggregation provides a solid foundation for decision-making in marketing, inventory, and finance.

## 📁 Deliverables

- ✅ online_sales table created and populated in PostgreSQL
- ✅ SQL aggregation query executed successfully
- ✅ Results exported as monthly_sales_summary_2024.png for reporting


---

✨ Done by: **Aditya Kankarwal**
## 📚 Key Learnings

- Practical use of EXTRACT() and GROUP BY for time-based trend analysis
- Using SUM() and COUNT(DISTINCT) for performance metrics
- How to filter results to specific timeframes and sort them meaningfully
- Real-world application of SQL in business analytics
