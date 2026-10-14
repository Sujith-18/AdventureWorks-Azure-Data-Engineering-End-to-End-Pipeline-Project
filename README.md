# DataCo-Supply-Chain-End-To-End-Project

# AdventureWorks End-to-End Data Engineering Project

## 📌 Project Overview

This project implements an end-to-end data engineering pipeline using Microsoft Azure services and the **Medallion Architecture**. The AdventureWorks dataset is ingested from GitHub, transformed using PySpark, and modeled into fact and dimension tables for analytical purposes.

## 🏗️ Architecture


AdventureWorks Dataset (Kaggle)
             |
             v
       GitHub Repository
             |
             v
   Azure Data Factory (ADF)
   Lookup + ForEach + Copy
             |
             v
      Bronze Layer
    (Raw Source Files)
             |
             v
    Azure Databricks
         PySpark
             |
    Data Cleaning and
     Transformation
             |
             v
      Silver Layer
     (Delta Format)
             |
             v
 Azure Synapse Analytics
    (Serverless SQL Pool)
             |
      SQL Views and
    Star Schema Modeling
             |
             v
       Gold Layer
   Fact and Dimension Tables

## 🛠️ Technologies Used

* **Azure Data Factory:** Dynamic data ingestion and pipeline orchestration.
* **Azure Data Lake Storage Gen2:** Storage for Bronze, Silver, and Gold layers.
* **Azure Databricks:** Data processing and transformation.
* **PySpark:** Data cleaning, validation, and transformation.
* **Delta Lake:** Storage format for Silver-layer data.
* **Azure Synapse Analytics:** SQL-based data exploration and modeling.
* **SQL:** Views, fact tables, dimension tables, and star schema modeling.
* **Microsoft Entra ID:** Application identity and authentication.

## 🔄 Implementation

### 1. Bronze Layer — Data Ingestion

* Downloaded the AdventureWorks dataset from Kaggle and uploaded the files to GitHub.
* Configured HTTP and Data Lake Storage linked services in Azure Data Factory.
* Used JSON configuration, Lookup, ForEach, and parameterized Copy activities to ingest multiple files dynamically.
* Stored the raw files in the Bronze container.

### 2. Silver Layer — Data Transformation

* Read the Bronze-layer files using Azure Databricks.
* Performed null handling, duplicate removal, data validation, and column name standardization using PySpark.
* Stored the transformed datasets in Delta format in the Silver container.

### 3. Gold Layer — Data Modeling

* Used Azure Synapse Serverless SQL Pool and `OPENROWSET` to query Silver-layer data.
* Created SQL views and developed fact and dimension tables.
* Implemented star schema modeling and performed data validation.
* Created external tables in the Gold layer for analytical queries.

## ⭐ Key Features

* Configuration-driven data ingestion using Azure Data Factory.
* End-to-end implementation of the Medallion Architecture.
* Data cleaning and transformation using PySpark.
* Delta Lake storage for transformed data.
* Star schema modeling with fact and dimension tables.
* SQL-based analytics using Azure Synapse Serverless SQL Pool.

## 🎯 Outcome

Built an end-to-end data engineering pipeline that ingests raw data, transforms it into clean datasets, and organizes it into analytics-ready fact and dimension tables using Microsoft Azure services.

