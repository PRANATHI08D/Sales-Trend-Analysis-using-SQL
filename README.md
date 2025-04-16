# Sales-Trend-Analysis-using-SQL
## Objective

This project focuses on analyzing monthly revenue and order volume from sales data to identify trends over time. The analysis is performed using SQL queries.

## Tools

* **Database:** PostgreSQL / MySQL / SQLite (The provided SQL script is compatible with these database systems)
* workbench :to load the dataset into the database

## Dataset

The analysis is performed on a table named  `UpdatedDetails`.

order_date (DATE): The date when the order was placed.
Amount (DECIMAL): The revenue from the order.
order_id (INTEGER): The unique identifier for the order.

## SQL Script (`sales_trend_analysis.sql`)
sql
-- SQL script to analyze monthly revenue and order volume
SELECT
  EXTRACT(YEAR FROM Order_date) AS year,
  EXTRACT(MONTH FROM Order_date) AS month,
  SUM(Amount) AS total_revenue,
  COUNT(DISTINCT Order_id) AS Order_volume
FROM
  updateddetails
GROUP BY
  EXTRACT(YEAR FROM Order_date),
  EXTRACT(MONTH FROM Order_date)
ORDER BY
  year, month; --
  
##Explanation:
EXTRACT(YEAR FROM order_date): Extracts the year part from the order_date.

EXTRACT(MONTH FROM order_date): Extracts the month part from the order_date.

SUM(amount): Calculates the total revenue per month.

COUNT(DISTINCT order_id): Counts the number of unique orders per month.

GROUP BY: Groups the data by year and month.

ORDER BY: Sorts the results by year and month in ascending order.

##Prerequisites
SQL Database (PostgreSQL / MySQL / SQLite)

Access to the updatedDetails dataset
