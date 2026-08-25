# Power BI Screenshots

## Overview

This folder contains screenshots of the Power BI dashboard developed for the Olist BI Retail Project.

The screenshots provide a visual overview of the dashboard pages, data model, KPIs, and business visualizations developed using Microsoft Power BI.

---

## 📊 Dashboard Pages

### 01 — Executive Overview

`01_Executive_Overview.png`

The Executive Overview provides a high-level view of the overall business performance.

Main elements include:

- Total Sales
- Total Orders
- Total Customers
- Average Order Value
- Sales performance
- Business performance overview

This page is designed to provide decision-makers with a quick overview of the main business KPIs.

---

### 02 — Sales Analysis

`02_Sales_Analysis.png`

The Sales Analysis page focuses on sales performance and revenue generation.

Main analyses include:

- Sales performance over time
- Sales by product category
- Sales by geographic area
- Order performance
- Freight value

This page helps identify sales trends and the main contributors to revenue.

---

### 03 — Customer Analysis

`03_Customer_Analysis.png`

The Customer Analysis page focuses on customer distribution and geographic analysis.

Main analyses include:

- Total Customers
- Top 10 Cities by Customers
- Customers by State
- Customer geographic distribution

This page helps identify major customer markets and geographic concentrations.

---

### 04 — Seller Analysis

`04_Seller_Analysis.png`

The Seller Analysis page evaluates seller performance.

Main analyses include:

- Total Sellers
- Top 10 Sellers by Sales
- Top 10 Sellers by Orders
- Seller performance analysis

This page allows comparison of sellers according to sales performance and order volume.

---

### 05 — Logistics Analysis

`05_Logistics_Analysis.png`

The Logistics Analysis page focuses on delivery performance and transportation costs.

Main analyses include:

- Total Orders
- Total Freight
- Average Freight per Order
- Average Delivery Time
- Freight Value by State

This page helps identify logistics performance and geographic differences in freight costs.

---

### 06 — Power BI Data Model

`06_Power_BI_Data_Model.png`

This screenshot presents the Power BI data model based on the Star Schema implemented in the PostgreSQL Data Warehouse.

The model includes:

- `fact_sales`
- `dim_customer`
- `dim_product`
- `dim_seller`
- `dim_order`
- `dim_date`
- `dim_payment`

The data model establishes the relationships required for interactive analysis and DAX calculations.

---

# 🔄 Power BI Analytical Flow

The screenshots represent the final Business Intelligence layer of the project:


PostgreSQL Data Warehouse
          ↓
      Power BI
          ↓
     Data Model
          ↓
     DAX Measures
          ↓
     KPI Cards
          ↓
    Visualizations
          ↓
 Interactive Dashboard
          ↓
   Business Insights
