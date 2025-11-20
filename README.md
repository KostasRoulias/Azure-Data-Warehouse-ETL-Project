# Azure-Data-Warehouse-ETL-Project
This is an end-to-end **Data Engineering project** built on Microsoft Azure, demonstrating a full ETL pipeline and a complete **Data Warehouse** modeled with a **star schema**.

The entire project uses:
- Azure Data Factory  
- Azure SQL Database  
- Azure Blob Storage  
- T-SQL  

---

## 📁 Project Overview

**Source:** Daily transactional banking CSV exported from an ERP system.

**Goal:**  
Build a complete DW pipeline:
1. Stage the raw file  
2. Build Dimension tables  
3. Load the Fact table with surrogate keys  
4. Implement star-schema modeling  

---

## 🏗️ Architecture

CSV → Azure Blob Storage → Data Factory Pipelines → SQL Stage Table → Dimensions → Fact Table

---

## 🔧 Technologies

- Azure Data Factory  
  - Linked Services  
  - Datasets  
  - Copy Data pipelines  
  - Mapping Data Flows  
- Azure SQL Database  
- Azure Blob Storage  
- SQL (DDL, DML)  

---

## 📊 Data Warehouse Schema

### ⭐ Dimension Tables
- `DIM_Category`
- `DIM_TransactionType`
- `DIM_TransactionCode`
- `DIM_Currency`
- `DIM_Account`
- `DIM_Date`

### ⭐ Fact Table
- `FACT_Transactions`

Using surrogate keys (`*_id`) for efficient joins and indexing.

---

## 🧱 ETL Pipelines

### 1️⃣ **PL_Stage_Transactions**
Loads the raw CSV file from Blob → SQL Stage table:
- TRUNCATE table  
- Copy data  
- Schema mapping  

### 2️⃣ **PL_Load_DIMs**
Loads all Dimension tables:
- DISTINCT queries on Stage layer  
- TRUNCATE + reload  
- Auto-populated surrogate keys  

### 3️⃣ **DF_Load_FACT_Transactions** (Mapping Data Flow)
Handles:
- Lookups from Stage to each Dimension  
- Date key conversions (YYYYMMDD)  
- Output mapping → Fact table  

---

## 📄 Included SQL Scripts
- Stage table creation  
- Dimension tables (DDL)  
- Fact table (DDL)  
- Verification queries  
- DISTINCT queries for dimension loads  

---

## 📝 What I Learned
- Azure Data Factory orchestration  
- Data Warehouse modeling (star schema)  
- Surrogate key design  
- ETL logic for full load + lookups  
- Building Fact tables using Mapping Data Flows  
- Debugging and monitoring cloud pipelines  

---

## 📷 Screenshots
- Database Schema (Star schema)
<img width="796" height="425" alt="Database Schema (Star schema)" src="https://github.com/user-attachments/assets/e9226d01-7a5e-434f-be5e-7b1c78cd6aa2" />


- 1st Pipeline_load data from CSV file to stage table
<img width="886" height="611" alt="1st pipeline" src="https://github.com/user-attachments/assets/1439e373-ba9b-4601-8618-5a273e5095ed" />


- 2nd Pipeline to load data from stage table to Dimensional tables and finally to Fact table
<img width="1084" height="247" alt="2nd Pipeline" src="https://github.com/user-attachments/assets/6d87939f-975b-44f2-abca-bfa7ea662990" />


- sql tables (DIM tables)  
<img width="256" height="583" alt="DIM tables" src="https://github.com/user-attachments/assets/931b648d-cf35-4fa9-8cf9-c6d61fd9a5f9" />


- sql tables (Fact and stage tables)
<img width="240" height="601" alt="Fact and stage tables" src="https://github.com/user-attachments/assets/36d3746d-b8a3-46c5-972f-1176c09ed9ef" />


- Fact table
<img width="1472" height="585" alt="Fact table" src="https://github.com/user-attachments/assets/5d35d05a-2dd5-4e0a-b1f0-7c09483b08ce" />


---

## 📬 Contact
- email: kostasroulias92@gmail.com
- linkedin: https://www.linkedin.com/in/konstantinosroulias/
