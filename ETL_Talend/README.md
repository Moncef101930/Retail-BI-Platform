# ETL with Talend

## Overview

This section presents the ETL pipeline developed with **Talend Open Studio** to integrate the Olist e-commerce dataset into the PostgreSQL Data Warehouse.

The ETL process follows:

**CSV Files → Staging Area → Data Warehouse**

## ETL Process

The pipeline performs:

- **Extract** — Read Olist CSV source files.
- **Transform** — Clean, convert and enrich the data using Talend.
- **Load** — Populate PostgreSQL staging and dimensional tables.
- **Integrate** — Connect dimensions with the `fact_sales` table using surrogate keys.

## Main Talend Components

- `tFileInputDelimited` — CSV ingestion
- `tDBInput` — PostgreSQL data extraction
- `tMap` — Transformations and joins
- `tDBOutput` — Database loading

## Data Transformations

Key transformations include:

- Data type conversion
- Date and timestamp processing
- Null value handling
- Dimension lookups
- Surrogate key retrieval
- Fact table measure calculation

## Data Warehouse Loading

The ETL populates the following dimensions:

`dim_customer` · `dim_product` · `dim_seller` · `dim_payment` · `dim_order` · `dim_date`

and the central fact table:

`fact_sales`

## Result

The final ETL pipeline provides a structured and reliable dataset ready for **Business Intelligence analysis and Power BI dashboards**.

**Tools:** Talend Open Studio · PostgreSQL · SQL  
**Methodology:** CRISP-DM  
**Architecture:** Star Schema
