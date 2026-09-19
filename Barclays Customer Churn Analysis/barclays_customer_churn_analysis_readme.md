# Barclays Customer Churn Analysis

An end-to-end Power BI business intelligence solution designed to analyze customer retention, identify churn drivers, and forecast attrition patterns across multiple European banking regions (France, Germany, Spain). 

This project integrates advanced data modeling, time-intelligence DAX measures, dynamic forecasting, and **Microsoft Copilot AI** to generate automated executive summaries and narrative insights.

---

## Executive Summary & Key KPIs

Across the portfolio of 10,000 banking customers analyzed, the report surfaces key performance indicators reflecting portfolio stability and risk exposure:

* **Total Customers:** 10,000
* **Portfolio Churn Rate:** 20.37%
* **Retained Customers:** 8,000
* **Exited Customers:** 2,000
* **Active vs. Inactive Base:** 5,000 Active Members | 5,000 Inactive Members

---

## Report Structure & Views

The Power BI report is organized into dedicated interactive views accessible via a custom navigation menu:

### 1. Executive Dashboard
* **Macro Portfolio Tracking:** High-level KPI cards with synchronized slicers for member activity status, gender, and credit product category.
* **Geographic Breakdown:** Total customers vs. exited customers segmented across France, Germany, and Spain.
* **Historical Run-Rate:** Dual-axis visual mapping monthly trends of total accounts, departures, and fluctuation in churn percentages.

### 2. Customer-Wise Analysis
* **Cohort Heatmap Matrix:** Tracks regional customer volume distributions across monthly cohorts.
* **Demographic & Salary Correlation:** Scatter plot analyzing relationship dynamics between customer age, estimated salary, and churn propensity, supported by correlation markers and animated playback.
* **Tenure & Loyalty Split:** Donut distribution evaluating average customer tenure relative to loyalty categorization.

### 3. Time Series & Predictive Analytics
* **Dynamic Time Intelligence:** Parameterized DAX metrics enabling switching across SPLY (Same Period Last Year), MTD, QTD, and YTD calculations.
* **Forecasting & Trend Models:** Built-in statistical forecasting projecting churn trajectory and account acquisitions into future quarters with defined confidence intervals.

### 4. AI-Driven Insights & Outcomes (Copilot Integration)
* **Automated Smart Narratives:** Utilizes Power BI's **Microsoft Copilot AI** integration to dynamically interpret visualizations, track variance, and generate natural language executive summaries.
* **Key AI-Generated Findings:**
  * France accounts for the largest customer concentration (5,014 accounts), 102.42% higher than Spain (2,477 accounts).
  * Germany exhibits the highest concentration of attrition, driving **39.96%** of all customer exits despite a smaller total account base.
  * Identifies steepest incline phases, portfolio expansion milestones, and churn velocity variances over multi-year evaluation periods.

### 5. Custom Tooltip Page
* Dedicated hover-activated report tooltip displaying instant drill-through cards for retained customers, exited volume, and localized churn rate.

---

## Data Model (Star Schema)

The analytical model is structured around a centralized **Star Schema** architecture optimized for high-performance DAX querying and bi-directional filtering control:

* **Fact Table:**
  * `Fact_Bank_Churn`: Contains transactional and customer status metrics (`Age`, `Balance`, `Bank DOJ`, `CreditScore`, `Credit Score tag`, `EstimatedSalary`, `Exited`, `Customer Remarks`).
* **Dimension Tables:**
  * `CustomerInfo`: Master demographics (`CustomerId`, `Surname`).
  * `Geography`: Regional mapping (`GeographyID`, `GeographyLocation`).
  * `Gender`: Demographic grouping (`GenderID`, `GenderCategory`).
  * `Credit_Card`: Product ownership (`CreditID`, `Category`).
  * `Active_Customer`: Platform engagement flag (`ActiveID`, `ActiveCategory`).
  * `Exit_Customer`: Attrition state lookup (`ExitID`, `ExitCategory`).
  * `Date_Dim`: Standardized calendar dimension (`Date`, `Day Name`, `Month`, `Month Name`, `Qtr`).

---

## Tech Stack & Features

* **Platform:** Microsoft Power BI Desktop
* **AI & Intelligence:** Microsoft Copilot in Power BI (Natural Language Insights, Variance & Trend Synthesis)
* **Modeling:** Dimensional Star Schema with 1:Many relationships
* **DAX Capabilities:** Custom KPI measures, dynamic time-series switching (MTD, QTD, YTD, SPLY), conditional formatting, and customized tooltip integration
* **Visuals:** Scatter plot correlation analysis, cohort matrices, forecasting with confidence intervals, donut charts, and custom page navigation buttons

---

## Repository Structure

```text
├── dataset/
│   └── bank_customer_churn.csv       # Raw source dataset
├── report/
│   └── barclays_churn_analysis.pbix  # Complete Power BI report file
├── assets/
│   ├── dashboard_home.png            # Cover page screenshot
│   ├── executive_dashboard.png       # Main KPI view screenshot
│   ├── customer_analysis.png         # Demographics & correlation view
│   ├── time_series_forecast.png      # Predictive analytics view
│   ├── ai_insights.png               # Copilot AI narrative view
│   └── data_model_schema.png         # Power BI Star Schema view
└── README.md
```

---

## Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/barclays-customer-churn-analysis.git
   ```
2. Open `report/barclays_churn_analysis.pbix` in **Microsoft Power BI Desktop**.
3. Interact with slicers, tooltips, and navigation tabs to explore dynamic customer segmentation and Copilot AI narratives.