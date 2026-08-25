# ETL Screenshots

## Overview

This folder contains screenshots illustrating the ETL implementation developed using **Talend Open Studio** for the Olist BI Retail Project.

The screenshots provide visual evidence of the different ETL jobs, transformations, dimension loading processes, fact table construction, and job execution.

---

## 📂 Screenshots

### 01 — ETL Job Architecture

`01_ETL_Job_Architecture.png`

This screenshot presents the overall architecture and organization of the ETL jobs developed in Talend.

It provides an overview of the different jobs involved in the data integration process.

---

### 02 — Customer Dimension ETL Job

`02_Customer_Dimension_ETL_Job.png`

This screenshot shows the Talend job responsible for transforming and loading customer data into the `dim_customer` table.

Main operations include:

- Data extraction
- Data transformation
- Data validation
- Loading into PostgreSQL

---

### 03 — Product Dimension ETL Job

`03_Product_Dimension_ETL_Job.png`

This screenshot presents the ETL workflow used to build the `dim_product` dimension.

The job prepares product information before loading it into the Data Warehouse.

---

### 04 — Seller Dimension ETL Job

`04_Seller_Dimension_ETL_Job.png`

This screenshot illustrates the ETL process used to create and populate the `dim_seller` dimension.

The workflow includes the transformation and loading of seller-related information.

---

### 05 — Order Dimension ETL Job

`05_Order_Dimension_ETL_Job.png`

This screenshot presents the ETL job responsible for constructing the `dim_order` dimension.

Order information is transformed and prepared for analytical use in the Data Warehouse.

---

### 06 — Date Dimension ETL Job

`06_Date_Dimension_ETL_Job.png`

This screenshot shows the ETL workflow used to populate the `dim_date` dimension.

The dimension provides the temporal structure required for time-based analysis in Power BI.

---

### 07 — Fact Sales ETL Job

`07_Fact_Sales_ETL_Job.png`

This screenshot presents the ETL workflow used to construct the `fact_sales` table.

The process integrates information from different staging and dimension tables to create the central fact table of the Star Schema.

Main elements include:

- Order information
- Customer information
- Product information
- Seller information
- Price
- Freight value
- Payment value
- Dimension keys

---

### 08 — ETL Job Execution

`08_ETL_Execution.png`

This screenshot provides evidence of the execution of the ETL process in Talend.

It illustrates the execution status and allows validation of the successful loading process.

---

## 🔄 ETL Workflow

The screenshots represent the following overall workflow:


Olist CSV Files
       ↓
     Talend
       ↓
Data Extraction
       ↓
Transformation
       ↓
Data Validation
       ↓
PostgreSQL Staging Area
       ↓
Dimension ETL Jobs
       ↓
Fact Sales ETL Job
       ↓
PostgreSQL Data Warehouse
       ↓
Power BI
