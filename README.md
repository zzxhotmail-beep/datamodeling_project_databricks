# Modern Data Pipeline with Data Modeling (Databricks)

## 📌 Overview

This project showcases an end-to-end data pipeline built on Databricks, with a strong emphasis on **data modeling for analytics**.

It follows the Medallion Architecture (Bronze–Silver–Gold) to transform raw transactional data into a structured **Star Schema**, designed for efficient analytical queries and business intelligence use cases.

## 🧠 Data Modeling Focus (Key Highlight)

A central focus of this project is designing scalable, analysis-ready data models that support downstream analytics.

### ⭐ Star Schema Design

The Gold layer is modeled using a **Star Schema**, separating data into fact and dimension tables:

- **Fact Table**
  - `FactTable` — transactional metrics (`quantity`, `unit_price`)

- **Dimension Tables**
  - `DimCustomers`
  - `DimProducts`
  - `DimPayments`
  - `DimRegions`
  - `DimSales`

This design enables:
- Efficient aggregations (e.g., revenue, sales trends)
- Simplified joins for analytical queries
- Improved performance for BI tools (Tableau, Power BI)

### 🔄 Slowly Changing Dimensions (SCD)

To handle evolving business data:

- **Type 1 (Overwrite)**  
  - Used for non-historical updates (e.g., correcting data)

- **Type 2 (Historical Tracking)**  
  - Preserves historical changes using versioning logic

This ensures the data model supports both **current-state analysis** and **historical insights**.

## 🏗️ Data Modeling Architecture (Bronze–Silver–Gold)

The pipeline progressively refines data across three layers:

### 🥉 Bronze Layer — Raw Data Ingestion

- Ingests raw data from source tables into the Bronze layer
- Implements **incremental data loading** based on `order_date`:
  - Retrieves the latest processed timestamp
  - Loads only new records (`order_date > last_load_date`)
- Stores data with minimal transformation

💡 Purpose:
- Preserve raw data  
- Avoid full reloads and improve efficiency  

### 🥈 Silver Layer — Data Cleaning & Transformation

- Cleans and enriches Bronze data
- Adds derived fields:
  - `customer_name_upper` (standardization)
  - `processDate` (processing timestamp)
- Implements **MERGE (upsert)** logic:
  - Updates existing records  
  - Inserts new records

💡 Purpose:
- Ensure data quality and consistency  
- Handle updates and historical tracking  
- Prepare structured datasets for modeling  

### 🥇 Gold Layer — Analytical Data Modeling

- Builds a **Star Schema** optimized for analytics

#### Dimension Tables:
- Deduplicated using `DISTINCT`
- Surrogate keys generated using `ROW_NUMBER()`

#### Fact Table:
- Stores core business metrics
- Joins all dimensions via surrogate keys

💡 Purpose:
- Enable fast analytical queries  
- Support dashboards and reporting  
- Provide a scalable foundation for business insights  

### 🔗 Data Flow

Raw Data → Bronze (Incremental Ingestion) → Silver (Cleaning + Upsert) → Gold (Star Schema)

## ⚙️ Tech Stack

- Databricks (Free Edition)
- SQL

## 🚀 Key Features

- End-to-end data pipeline implementation
- Medallion Architecture (Bronze / Silver / Gold)
- **Star Schema data modeling** ⭐
- Incremental data ingestion
- MERGE (upsert) logic in Silver layer
- Slowly Changing Dimensions (Type 1 & Type 2)

## 📊 Example Analytical Use Cases

The final data model supports:

- Revenue analysis by region and product  
- Customer segmentation  
- Payment behavior analysis  
- Time-based sales trends  

## ▶️ How to Run

1. Load source data into Databricks  
2. Run Bronze ingestion logic (incremental load)  
3. Run Silver transformation logic (cleaning, upsert)  
4. Run Gold layer modeling (Star Schema)  

## 👤 Author - Zixuan Zhang

This project demonstrates my ability to design and implement data models and pipelines that transform raw data into actionable insights — combining data engineering and analytics skills.

- **LinkedIn**: [My Professional Profile](https://www.linkedin.com/in/zixuan-zhang-78ba38274)
