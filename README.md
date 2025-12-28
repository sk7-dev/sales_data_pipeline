# End-to-End Azure Data Pipeline Project

## 📌 Project Overview
This project demonstrates a **full-scale end-to-end data engineering pipeline** built on **Microsoft Azure**.  
It covers **data ingestion, storage, transformation, analytics, and visualization** using industry-standard tools.

The pipeline ingests data from an **on-premises SQL Server**, processes it using a **Medallion Architecture (Bronze → Silver → Gold)**, and delivers insights through an **interactive dashboard**.

---

## 🏗️ Architecture Overview

![Architecture Workflow](https://github.com/sk7-dev/sales_data_pipeline/blob/main/Images/Workflow.png)

### Architecture Components
- **Source**: On-Prem SQL Server (AdventureWorks)
- **Ingestion**: Azure Data Factory
- **Storage**: Azure Data Lake Gen2
- **Processing**: Azure Databricks (Bronze → Silver → Gold)
- **Analytics**: Azure Synapse Analytics
- **Visualization**: Power BI
- **Security & Governance**: Azure Active Directory, Azure Key Vault

---

## 🔄 Data Pipeline Flow

![ADF Pipeline](https://github.com/sk7-dev/sales_data_pipeline/blob/main/Images/azp1_Pipeline.PNG)

### Pipeline Steps
1. **Lookup Activity**
   - Dynamically retrieves all table names from the source database
2. **ForEach Activity**
   - Iterates over tables and copies data to Data Lake (Bronze Layer)
3. **Databricks Notebook – Bronze to Silver**
   - Data cleansing, schema enforcement, standardization
4. **Databricks Notebook – Silver to Gold**
   - Aggregations, business logic, analytics-ready datasets

---

## ⏰ Pipeline Scheduling & Monitoring

![ADF Trigger Runs](https://github.com/sk7-dev/sales_data_pipeline/blob/main/Images/azp1_pipeline_trigger.PNG)

- **Scheduled Trigger** runs daily
- Successful executions monitored via **ADF Trigger Runs**
- Enables **automated and reliable data refresh**

---

## ☁️ Azure Resource Group

![Azure Resource Group](https://github.com/sk7-dev/sales_data_pipeline/blob/main/Images/azp1_resource_group.PNG)

### Deployed Azure Services
- Azure Data Factory
- Azure Databricks
- Azure Data Lake Storage Gen2
- Azure Synapse Analytics
- Azure Key Vault

All resources are deployed within a **single resource group** for centralized management.

---

## 🗄️ Source System – On-Prem SQL Server

![On-Prem SQL Server](https://github.com/sk7-dev/sales_data_pipeline/blob/main/Images/On-prem_db.PNG)

- Database: **AdventureWorks**
- Tables ingested:
  - SalesLT.Customer
  - SalesLT.Product
  - SalesLT.SalesOrderHeader
  - SalesLT.SalesOrderDetail
  - Product, Category, Address tables

---

## 📊 Analytics & Visualization Dashboard

![Sales Dashboard](https://github.com/sk7-dev/sales_data_pipeline/blob/main/Images/Dashboard4.PNG)

### Dashboard Insights
- **Total Sales**
- **Total Orders**
- **Number of Products**
- **Top 10 Best-Selling Products**
- **Sales by Category**
- **Price vs Sales Analysis**
- Interactive slicers for category and price range

Built using **Power BI** on top of curated **Gold Layer** data.

---

## 🥇 Medallion Architecture

| Layer | Description |
|-----|------------|
| **Bronze** | Raw ingested data from SQL Server |
| **Silver** | Cleaned, standardized, validated data |
| **Gold** | Aggregated, analytics-ready datasets |

---

## 🔐 Security & Governance
- **Azure Active Directory** for authentication
- **Azure Key Vault** for secrets management
- Secure access between ADF, Databricks, and Storage

---

## 🛠️ Technologies Used

- Azure Data Factory
- Azure Databricks
- Azure Data Lake Gen2
- Azure Synapse Analytics
- Azure SQL Server
- Power BI
- Python (PySpark)
- SQL

---

## 🎯 Key Learnings
- Building scalable cloud data pipelines
- Implementing Medallion Architecture
- Automating ingestion using ADF
- Data transformations with Databricks
- Enterprise-grade security in Azure
- Delivering insights through dashboards

---

## 📌 Future Enhancements
- Incremental data loads (CDC)
- CI/CD with Azure DevOps
- Data quality checks
- Cost optimization strategies
- Streaming ingestion with Event Hub



---

⭐ *If you found this project useful, feel free to star the repository!*
