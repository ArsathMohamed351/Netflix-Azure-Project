# 🎬 Netflix Data Engineering Project  
### End-to-End Data Pipeline using Azure Databricks & Delta Live Tables

## 📌 Project Overview
This project implements an **end-to-end data engineering pipeline for Netflix-style analytical data** using **Azure Databricks** and **Delta Live Tables (DLT)**.  
The pipeline processes raw Netflix datasets, applies data quality rules, builds a **medallion architecture (Bronze → Silver → Gold)**, and delivers **analytics-ready data** for reporting and insights.

The final curated datasets are modeled using a **Star Schema** and exposed to **Azure Synapse Analytics** and **Power BI** for business reporting.

---

## 🏗️ High-Level Architecture
<img width="1920" height="1080" alt="Architecture" src="https://github.com/user-attachments/assets/a594b1d5-4007-43d6-8c7a-dfc91a53a8aa" />


### Architecture Components
- **Azure Data Factory** – Orchestrates ingestion workflows
- **Azure Data Lake Gen2** – Central storage for all layers
- **Azure Databricks** – Data processing and transformations
- **Delta Live Tables (DLT)** – Managed ETL pipelines
- **Azure Synapse Analytics** – Data warehouse layer
- **Power BI** – Reporting & visualization
- **GitHub** – Version control and CI/CD
- **Azure AD & Key Vault** – Security and secrets management

---

## 🧱 Medallion Architecture
| Layer | Description |
|-----|------------|
| **Bronze (Raw)** | Incremental ingestion of Netflix source data |
| **Silver (Cleaned)** | Data cleansing, lookups, standardization |
| **Gold (Serving)** | Star schema tables for analytics & reporting |

---

## ⚙️ Technologies Used
- Azure Databricks
- Delta Live Tables (DLT)
- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Synapse Analytics
- Power BI
- PySpark
- Apache Spark
- GitHub

---

## 🔄 Data Pipeline Flow
1. Netflix source data ingested via **Azure Data Factory**
2. Raw incremental data stored in **ADLS Gen2 (Bronze)**
3. Data transformed into **Silver layer** using Databricks notebooks
4. **Delta Live Tables** build Gold tables with data quality rules
5. Star schema created for analytical workloads
6. Data served to **Azure Synapse**
7. Insights visualized using **Power BI**

---

## 🧪 Delta Live Tables (DLT)
<img width="1919" height="982" alt="Screenshot 2026-01-14 105808" src="https://github.com/user-attachments/assets/2d3c5ebe-c8c4-47b0-9512-b6fcf95bcd2f" />


### Data Quality Rules Example
```python
masterdata_rules = {
    "rule1": "newflag IS NOT NULL",
    "rule2": "show_id IS NOT NULL"
}
