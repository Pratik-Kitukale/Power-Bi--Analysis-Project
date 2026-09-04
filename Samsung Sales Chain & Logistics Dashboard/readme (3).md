# 📱 Samsung Sales Chain & Logistics Dashboard

## 📌 Project Overview
This project is an end-to-end **Data Analytics** and **Business Intelligence** solution designed to monitor, analyze, and optimize the supply chain operations of a global consumer electronics brand. By integrating data across multiple logistical stages, this dashboard provides actionable insights into supplier performance, inventory management, shipping logistics, and customer sales to support data-driven decision-making.

## 🛠️ Tech Stack & Skills Demonstrated
* **Database & Data Extraction:** SQL (Relational database querying, data structuring)
* **Business Intelligence:** Microsoft Power BI
* **Data Transformation:** Power Query
* **Calculations & Modeling:** DAX (Data Analysis Expressions), Star/Snowflake Schema Design

## 🗄️ Data Model Architecture
The project utilizes a highly optimized relational data model to ensure efficient cross-filtering and high-performance DAX calculations.

| Table Type | Table Name | Key Metrics / Data Points |
| :--- | :--- | :--- |
| **Fact** | `fact_sales` | Transactional revenue, discount, profit |
| **Fact** | `fact_shipment` | Logistics tracking, delivery delays, carrier metrics |
| **Fact** | `fact_inventory` | Stock levels, reorder points, safety stock |
| **Fact** | `fact_procurement` | Order quantities, lead time, quality scores |
| **Fact** | `fact_production` | Defect rates, batch quantities |
| **Dimension** | `dim_product` | Categories, product lines, unit costs |
| **Dimension** | `dim_supplier` | Supplier geography, specialty |
| **Dimension** | `dim_customer` | Customer locations, channel types, size |
| **Dimension** | `dim_facility` | Warehouse locations, storage capacities |
| **Dimension** | `dim_date` | Standard time intelligence calendar |

## 📊 Dashboard Pages & Business Insights

### 1. Overview 
Acts as the executive summary, presenting high-level KPIs across the entire supply chain.
* **Key Metrics:** Total Revenue ($176.95M), Total Profit ($48.56M), Profit Margin (27.44%), Order QTY (129K).
* **Highlights:** Tracks gross revenue, total shipment volume, and overall perfect order percentages alongside top-level supplier lead times and total carrier delays.

### 2. Supplier Analysis
Evaluates vendor efficiency, cost-effectiveness, and reliability.
* **Key Metrics:** Total Unit Cost, Avg Lead Time (11.53 Days), Total Suppliers (7).
* **Highlights:** Lead time comparisons across key manufacturing regions (China, Japan, South Korea, Taiwan) and strict quality score tracking for top manufacturers like TSMC and Samsung Electronics.

### 3. Inventory Management
Focuses on warehouse efficiency, stock availability, and manufacturing quality control.
* **Key Metrics:** Safety Stock (89K), Turnover Rate (85%), Days of Inventory (427).
* **Highlights:** Features a dynamic visual comparison of Current Stock vs. Safety Stock vs. Reorder Point by specific product models, alongside historical defect rate tracking to identify production flaws early.

### 4. Shipment & Logistics
Monitors the physical movement of goods and identifies transit bottlenecks.
* **Key Metrics:** Total Shipment Cost ($229.80K), Total Delays (12), Delivered % (76%).
* **Highlights:** Granular delivery status distribution, carrier-specific delay breakdowns (FedEx, DHL, UPS), and root-cause analysis for delays (e.g., Documentation issues, Port Congestion, Carrier Capacity).

### 5. Customer & Sales
Analyzes revenue streams, discounting strategies, and profitability by sales channel.
* **Key Metrics:** Total Discount ($9.92M), Gross Revenue ($186.86M).
* **Highlights:** Analyzes Revenue vs. Profit vs. Growth MoM, evaluates revenue distribution by channel type (Direct, Online, Retailer), and highlights top-performing platforms (Amazon, Best Buy).

## 📈 Advanced DAX Measures
Over 20 custom DAX measures were authored to extract precise business logic. Notable calculations include:
* **`Perfect Order %`**: Calculates the percentage of orders delivered without delays or defects, serving as a primary logistics KPI.
* **`Profit Margin %`**: Dynamically calculates profitability utilizing `DIVIDE([Total Profit], [Total Revenue], 0)`.
* **`Days of Inventory`**: Measures how long current warehouse stock will last based on historical sales velocity.
* **`Defect Rate`**: Tracks `fact_production[defective_units]` against total output to ensure quality standards.

## 🚀 How to Run Locally
1. Clone this repository to your local machine:
   ```bash
   git clone [https://github.com/your-username/samsung-logistics-dashboard.git](https://github.com/your-username/samsung-logistics-dashboard.git)