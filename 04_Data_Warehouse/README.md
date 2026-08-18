# Data Warehouse

This folder contains the design and implementation of the **Olist Data Warehouse**, developed as part of the **Retail BI Platform** project.

The Data Warehouse transforms data from the Staging Area into a structured analytical model designed for Business Intelligence and reporting.

---

## 1. Objective

The main objectives of the Data Warehouse are:

- Centralize and structure business data for analytical purposes.
- Transform operational data into an analytical model.
- Provide reliable data for reporting and KPI analysis.
- Facilitate multidimensional analysis.
- Prepare the data for Power BI dashboards.

---

## 2. Architecture

The Data Warehouse follows a **Star Schema** architecture.

It consists of:

- One central fact table: `fact_sales`
- Six dimension tables:
  - `dim_customer`
  - `dim_product`
  - `dim_seller`
  - `dim_payment`
  - `dim_order`
  - `dim_date`

### Star Schema

The `fact_sales` table is connected to the dimension tables through surrogate keys.


                        dim_customer
                              |
                              |
dim_product ----------- fact_sales ----------- dim_seller
                              |
                    ┌─────────┼─────────┐
                    |         |         |
              dim_payment  dim_order  dim_date
