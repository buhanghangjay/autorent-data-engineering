# 🚗 AutoRent Data Engineering Pipeline

An end-to-end Azure data engineering project that transforms raw car rental data into clean, validated, analytics-ready datasets using a Bronze, Silver, and Gold architecture.

---

## 📌 Project Overview

AutoRent is a fictional car rental company that generates operational data for:

- Cars
- Customers
- Employees
- Locations
- Rental Transactions

The objective of this project is to build an automated ETL pipeline that ingests multiple daily source datasets, cleans and transforms the data, preserves historical dimension changes, creates an analytics-ready dimensional model, and orchestrates the workflow using Azure services.

---

## 🏗️ Architecture

The solution follows a layered data architecture:

Source Data  
↓  
Azure Data Lake Storage Gen2  
↓  
Bronze Layer  
↓  
Azure Databricks / PySpark  
↓  
Silver Layer  
↓  
SCD Type 2 Processing  
↓  
Gold Layer  
↓  
Databricks Workflow  
↓  
Azure Data Factory Orchestration

### Data Layers

**Bronze Layer**
- Stores raw AutoRent source files.
- Maintains Day 1, Day 2, and Day 3 source batches.
- Preserves source data for traceability.

**Silver Layer**
- Cleans and standardizes source data.
- Converts data types.
- Handles null values and data-quality issues.
- Detects duplicate records.
- Stores transformed data in Delta format.

**Gold Layer**
- Contains analytics-ready dimensions and Fact data.
- Implements Slowly Changing Dimension Type 2.
- Uses surrogate keys for dimensional relationships.
- Provides validated datasets for downstream analytics.

---

## 🛠️ Technologies Used

- **Azure Data Lake Storage Gen2** – Data storage
- **Azure Databricks** – Data processing and transformation
- **Apache Spark / PySpark** – ETL development
- **Delta Lake** – Curated Delta table storage
- **Databricks Workflows** – ETL job automation
- **Azure Data Factory** – Pipeline orchestration
- **GitHub** – Version control and project repository

---

## 🥉 Bronze Layer

The Bronze layer contains the raw daily AutoRent datasets:

```text
Cars
Customers
Employees
Locations
Transactions