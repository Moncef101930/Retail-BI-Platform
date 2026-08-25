# Olist BI Retail Project

## Business Intelligence & Data Analytics Platform

An end-to-end Business Intelligence project based on the Olist Brazilian E-Commerce dataset.

The objective of this project is to design and implement a complete BI platform, starting from raw data ingestion and ETL processes, through Data Warehouse modeling, and ending with interactive Power BI dashboards and advanced analytics.

---

## 📌 Project Overview

The project follows a structured Business Intelligence architecture:

Raw Data → ETL → Staging Area → Data Warehouse → Power BI → Business Insights

The solution is designed to transform raw e-commerce data into reliable, structured, and actionable information for business decision-making.

The project covers several areas:

- Sales performance
- Customer analysis
- Seller performance
- Product analysis
- Logistics performance
- Geographic analysis
- Business KPIs
- Interactive reporting

---

## 🎯 Business Objectives

The main objectives of the project are to:

- Analyze overall e-commerce performance.
- Monitor sales and order trends.
- Identify high-performing product categories.
- Analyze customer distribution and behavior.
- Evaluate seller performance.
- Analyze logistics and delivery performance.
- Monitor freight costs.
- Provide interactive dashboards for business users.
- Build a scalable BI architecture for future analytics and automation.

---

# 🏗️ Solution Architecture


                    Olist Datasets
                          │
                          ▼
                    CSV Source Files
                          │
                          ▼
                       Talend
                  ETL / Data Integration
                          │
                          ▼
                  PostgreSQL Staging
                    Staging Area
                          │
                          ▼
                 Transformation Layer
                          │
                          ▼
              PostgreSQL Data Warehouse
                    Star Schema
                          │
             ┌────────────┼─────────────┐
             │            │             │
             ▼            ▼             ▼
          Power BI    Machine Learning   n8n
          Dashboard    & Predictions   Automation
             │
             ▼
       Business Insights
