# 🎵 Azure End-to-End Data Engineering Project – Spotify Data

## 📌 Project Overview

This project implements a **real-world end-to-end data engineering pipeline on Azure** using the Spotify dataset.  
It showcases how to design **scalable, incremental, and analytics-ready pipelines** using **Azure Data Factory, Azure Databricks, Delta Lake, and Power BI**.

The solution ingests data incrementally from **Azure SQL Database**, processes it through **Bronze, Silver, and Gold layers**, applies **Slowly Changing Dimensions**, enforces **data quality checks**, and delivers curated datasets for business reporting.

🏗️ **Architecture Overview:**

<img width="1020" height="544" alt="Screenshot 2026-01-11 191214" src="https://github.com/user-attachments/assets/2e66c2bb-625c-4942-81d9-ad43af83be4a" />

## 🛠️ Technologies Used

- **Cloud:** Microsoft Azure  
- **Role Focus:** Azure Data Engineer  
- **Core Skills:** ADF, Azure Databricks, Delta Lake, Unity Catalog, Lakeflow, Power BI  
- **Architecture:** Medallion (Bronze → Silver → Gold)  
- **Ingestion Type:** Incremental (CDC-based)  
- **Modeling:** Fact & Dimension tables with SCD Type 1 & Type 2  
- **Deployment:** Databricks Asset Bundles (CI/CD ready)

## 🧱 Key Design Principles

✔ Medallion Architecture (Bronze / Silver / Gold)  
✔ Incremental ingestion using CDC  
✔ Parameterized & reusable pipelines  
✔ Metadata-driven transformations  
✔ Declarative data pipelines (Lakeflow)  
✔ Schema evolution with Delta Lake  
✔ Data quality expectations  
✔ Enterprise-ready deployment using Asset Bundles  

---

## 🔄 End-to-End Data Flow

### 1️⃣ Data Ingestion – Bronze Layer (Azure Data Factory)

- Source system: **Azure SQL Database**
- Built **parameterized incremental pipelines** using CDC
- Key ADF activities:
  - Lookup – Read CDC metadata
  - Set Variable – Store current load timestamp
  - Copy – Incremental load to ADLS Gen2
  - Script – Capture max CDC value
  - Copy – Update CDC JSON recursively
- **Backfilling supported** for historical data loads
- Raw data stored in **Bronze layer**

---

### 2️⃣ Data Processing – Silver Layer (Azure Databricks)

- Configured **Databricks Unity Catalog** for governance
- Deployed notebooks and pipelines using **Databricks Asset Bundles**
- Used **Databricks Auto Loader** for incremental ingestion
- Transformations applied:
  - Deduplication
  - Null handling
  - Data type casting
  - Column standardization
- Output stored as **Delta tables** in Silver layer

---

### 3️⃣ Data Modeling – Gold Layer (Lakeflow Declarative Pipelines)

- Built **Lakeflow declarative pipelines** for maintainable transformations
- Created analytics-ready star schema

#### Dimension Tables (SCD Type 2)
- `DimUser`
- `DimTrack`
- `DimArtist`
- `DimDate`

#### Fact Table
- `FactStream` (SCD Type 1 – UPSERT)

- Enabled **incremental processing**
- Added **data quality expectations** for validation

---

### 4️⃣ Metadata-Driven Business Views

- Developed **metadata-driven pipelines using Jinja templates**
- Dynamically joins fact and dimension tables
- Enables rapid onboarding of new reporting requirements
- No code changes required for new stakeholders

---

### 5️⃣ Analytics & Reporting

- Integrated Gold layer Delta tables with **Power BI**
- Enabled incremental refresh
- Built dashboards for Spotify streaming analytics

---

## 🛠️ Technologies & Tools

**Cloud & Storage**
- Azure SQL Database
- Azure Data Lake Storage Gen2

**Orchestration**
- Azure Data Factory (ADF)

**Processing & Modeling**
- Azure Databricks
- Delta Lake
- Auto Loader
- Lakeflow Declarative Pipelines
- Unity Catalog

**Deployment & Frameworks**
- Databricks Asset Bundles
- Jinja Templates
- JSON metadata

**Analytics**
- Power BI

---

## ▶️ How to Run the Project

1. Provision Azure resources (SQL DB, ADLS, ADF, Databricks)
2. Configure Unity Catalog
3. Deploy Databricks assets using Asset Bundles
4. Configure ADF linked services and CDC metadata
5. Run ADF pipeline (incremental or backfill)
6. Execute Bronze → Silver → Gold pipelines
7. Validate SCD logic and data quality
8. Connect Power BI to Gold tables

---

## ⭐ Resume-Ready Highlights

- Designed and implemented **end-to-end Azure data engineering pipeline**
- Built **incremental ingestion framework using CDC and Azure Data Factory**
- Implemented **Medallion Architecture with Delta Lake**
- Developed **SCD Type 2 dimensions and SCD Type 1 fact tables**
- Used **Databricks Auto Loader and Lakeflow declarative pipelines**
- Created **metadata-driven transformations using Jinja templates**
- Enforced **data quality expectations**
- Deployed Databricks workloads using **Asset Bundles**
- Integrated curated data with **Power BI dashboards**

---

## 🧾 Conclusion

This project demonstrates **enterprise-grade Azure data engineering practices**, including incremental ingestion, scalable transformations, declarative modeling, governance, and analytics enablement. It reflects real-world patterns used in modern data platforms and is suitable for production deployments.

---









