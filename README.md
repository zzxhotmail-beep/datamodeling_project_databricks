# Modern Data Pipeline with Data Modeling (Databricks)

## 📌 Overview

This project demonstrates an end-to-end data pipeline built on Databricks, with a strong focus on **data modeling for analytics**. 

The pipeline follows the Medallion Architecture (Bronze, Silver, Gold) and transforms raw transactional data into a structured **Star Schema** optimized for analytical queries and business intelligence.

## 🧠 Data Modeling Focus (Key Highlight)

A core part of this project is designing scalable and analysis-friendly data models:

### ⭐ Star Schema Design

The Gold layer is modeled using a **Star Schema**, separating:

- **Fact Table**
  - `fact_transactions`

- **Dimension Tables**
  - `dim_customers`
  - `dim_products`
  - `dim_payments`
  - `dim_regions`
  - `dim_sales`

This structure enables:
- Efficient aggregation queries
- Simplified joins
- Better performance for BI tools

### 🔄 Slowly Changing Dimensions (SCD)

To handle evolving business data:

- **Type 1 (Overwrite)**  
  - Used for non-historical updates (e.g., correcting product names)

- **Type 2 (Historical Tracking)**  
  - Maintains full history using versioning and effective dates

## 🏗️ Architecture

Source → Bronze → Silver → Gold

- **Bronze**: Raw ingestion from source  
- **Silver**: Cleaned, deduplicated, enriched data  
- **Gold**: Business-level data modeling (Star Schema)

## ⚙️ Tech Stack
- Databricks (Free Edition)
- SQL

## 🚀 Key Features

- Medallion Architecture (Bronze / Silver / Gold)
- Star Schema Data Modeling ⭐
- Merge (Upsert) Logic in Silver Layer
- Slowly Changing Dimensions (Type 1 & Type 2)

## 📊 Example Analytical Use Cases

- Revenue analysis by region and product
- Customer segmentation
- Payment method analysis
- Time-based sales trends

## ▶️ How to Run

1. Load source data into Databricks
2. Run Bronze ingestion logic
3. Run Silver transformation logic
4. Run Gold modeling (Star Schema)

## 👤 Author - Zixuan Zhang

This portfolio project demonstrates my proficiency in data modeling using Databricks, with a focus on building scalable data pipelines and analytical data models (Star Schema) — key skills for Data Analyst and Data Engineering roles.

- **LinkedIn**: [My Professional Profile](https://www.linkedin.com/in/zixuan-zhang-78ba38274)
