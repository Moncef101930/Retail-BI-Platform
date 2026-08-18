# Staging Area

## Overview

The Staging Area is the intermediate layer of the **Retail BI Platform** data pipeline.

It is used to temporarily store the data extracted from the Olist CSV files before applying the transformations required for the Data Warehouse.

The Staging Area provides a controlled environment for data ingestion, validation, and preparation while preserving the original source structure.

---

## Objectives

The main objectives of the Staging Area are:

- Ingest raw Olist datasets into PostgreSQL.
- Preserve the source data before transformation.
- Centralize the different CSV datasets in a relational environment.
- Validate the structure and data types of incoming data.
- Prepare data for the ETL transformation process.
- Separate raw data ingestion from Data Warehouse processing.
- Facilitate data quality checks and troubleshooting.

---

## Architecture

The data pipeline follows the following architecture:


Olist CSV Files
      |
      v
Talend Open Studio
      |
      | Data Extraction
      v
PostgreSQL
      |
      v
Staging Area
      |
      | Transformation & Cleaning
      v
Data Warehouse
      |
      v
Power BI
