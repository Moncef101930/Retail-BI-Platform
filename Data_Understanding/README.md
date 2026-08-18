# Data Understanding

## Overview

This folder contains the **Data Understanding** phase of the Retail BI Platform project, following the **CRISP-DM methodology**.

The objective of this phase is to explore the Olist e-commerce dataset, understand its structure and business meaning, identify relationships between datasets, and assess the overall quality of the available data before starting the data preparation and Data Warehouse development phases.

---

## Objectives

The main objectives of the Data Understanding phase are:

- Identify and describe the available datasets.
- Understand the structure and meaning of each attribute.
- Analyze the relationships between datasets.
- Identify primary and foreign key relationships.
- Explore data distributions and business patterns.
- Detect missing values and potential data quality issues.
- Identify duplicates and inconsistent values.
- Determine which datasets are relevant for the BI solution.
- Prepare the foundation for the Data Warehouse design.

---

## Dataset

The project uses the **Olist Brazilian E-Commerce Public Dataset**, which contains information about orders, customers, products, sellers, payments, reviews, and geographic data.

The dataset is composed of several CSV files representing different business entities and processes.

### Main datasets

| Dataset | Description | Main Key |
|---|---|---|
| `olist_orders_dataset.csv` | Order information and order lifecycle | `order_id` |
| `olist_order_items_dataset.csv` | Products included in each order | `order_id`, `order_item_id` |
| `olist_order_payments_dataset.csv` | Payment information associated with orders | `order_id` |
| `olist_customers_dataset.csv` | Customer information and location | `customer_id` |
| `olist_products_dataset.csv` | Product characteristics | `product_id` |
| `olist_sellers_dataset.csv` | Seller information and location | `seller_id` |
| `olist_order_reviews_dataset.csv` | Customer reviews and ratings | `review_id`, `order_id` |
| `olist_geolocation_dataset.csv` | Brazilian geographic information | `geolocation_zip_code_prefix` |
| `product_category_name_translation.csv` | Product category translation | `product_category_name` |

---

## Data Architecture

The main relationships identified during the exploration are:

                         Customers
                             |
                             | customer_id
                             |
                             v
Orders ----------------> Order Items <---------------- Products
   |                         |
   |                         |
   v                         v
Payments                  Sellers
   |
   |
   v
Reviews
