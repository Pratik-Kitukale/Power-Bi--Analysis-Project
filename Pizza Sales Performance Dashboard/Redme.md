# Pizza Sales Performance Analysis 🍕📊

## About the Project
This project provides a comprehensive data analytics solution for a pizza retail business. By extracting and analyzing raw sales data using MySQL and visualizing it in an interactive Power BI dashboard, this project uncovers actionable insights regarding revenue trends, customer ordering patterns, and product performance. 

## Data Source
* **Dataset:** `pizza_sales.xlsx`

## Tools & Technologies
* **Database Management:** MySQL (Data Extraction, KPI Calculation, Trend Analysis)
* **Data Visualization:** Power BI (Interactive Dashboard Creation, Data Modeling)

## Key Performance Indicators (KPIs)
The following fundamental business metrics were formulated and calculated during the analysis[cite: 1]:
* **Total Revenue:** Sum of the total price of all pizza orders[cite: 1].
* **Total Orders:** Count of distinct orders placed[cite: 1].
* **Average Order Value:** Total revenue divided by the number of total orders[cite: 1].
* **Total Pizzas Sold:** Sum of the quantities of all pizzas sold[cite: 1].
* **Average Pizzas Per Order:** Total pizzas sold divided by total orders[cite: 1].

## SQL Data Analysis & Business Insights
Comprehensive SQL queries were executed to extract the following business insights[cite: 1]:
* **Revenue & Order Trends:** Grouping data by day and month to identify peak sales periods and track monthly revenue trends[cite: 1].
* **Sales Distribution:** Calculating the percentage of total sales based on pizza category (Classic, Supreme, Chicken, Veggie) and size (Large, Medium, Small, X-Large, XX-Large)[cite: 1].
* **Top & Bottom Performers:** Ranking the pizza catalog by Revenue, Total Orders, and Quantity Sold to identify the top 5 and bottom 5 performing items[cite: 1].

### Sample SQL Queries Used
```sql
-- Calculate Total Revenue
SELECT SUM(TOTAL_PRICE) AS TOTAL_REVENUE FROM PIZZA_SALES;

-- Calculate Percentage of Sales by Pizza Category
SELECT PIZZA_CATEGORY, SUM(TOTAL_PRICE) AS TOTAL_REVENUE,
CAST(SUM(TOTAL_PRICE)*100/ 
(SELECT SUM(TOTAL_PRICE) FROM PIZZA_SALES) AS DECIMAL(10,2)) AS PCT
FROM PIZZA_SALES
GROUP BY PIZZA_CATEGORY;

-- Identify Top 5 Pizzas by Revenue
SELECT PIZZA_NAME, SUM(TOTAL_PRICE) AS TOTAL_REVENUE
FROM PIZZA_SALES
GROUP BY PIZZA_NAME
ORDER BY TOTAL_REVENUE DESC
LIMIT 5;