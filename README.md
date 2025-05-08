
# 📦 Telecom ETL Project – SSIS Package

## 🚀 Project Overview
This project demonstrates the full ETL lifecycle for a telecom dataset using **SSIS**, **CSV**

### 🔍 Objectives:
- Load and transform telecom CSV data into a data warehouse.
- Apply auditing to monitor ETL performance and trace package execution.
- Track historical changes using **SCD Type 2**.

---

## ⚙️ Technologies Used
- **CSV** – Source 
- **SQL Data Warehouse** – Destination  
- **SSIS** – ETL development (Dervied Columus - looping and Archieving- ERROR Handling - Auditing)
- **T-SQL** – Data queries and transformations

---

## 🧠 Key ETL Features

### 🔄 ETL Flow:
- **Source**: Telecom sales and customer data
- **Transformations**:
  - Lookup
  - Derived Columns
  - Conditional Splits
  - looping
  - Auditing
- **Destination**: Data Warehouse loading


### 🕵️‍♀️ Auditing Logic:
Implemented to track:
- Package Name
- Execution Time
- Machine Name
- User Name
- Execution Status

#### ✅ Benefits of Auditing:
- Helps troubleshoot failed package runs
- Enhances visibility into ETL behavior
- Supports data governance and compliance

---

## 🧱 Looping & Archiving CSV Files

-Foreach Loop Container to Automate File Processing
-Utilized the Foreach Loop Container to dynamically loop through multiple CSV files in a specified directory and process them one by one.
-SSIS variables were configured to capture and pass each file name to the Data Flow Task, allowing the same package to handle different files without modification.

After each file was processed, it was automatically moved to an “Archive” folder using the File System Task, ensuring a clean input directory and traceability of processed files.
---
---

## 🛠️ Project Screenshots

### 🎯 ETL Packages:
- Creation Datawarehousing:
  ![Creation-Datawarehousing](https://github.com/Marwamedha/SSIS-Packages/blob/main/Etl%20Packages/Creation%20Database.png)
- Fact Table:
  ![Fact Sales Package](https://github.com/Marwamedha/SSIS-Packages/blob/main/Etl%20Packages/Fact%20Table%20Creation.png)
- SCD Logic:
  ![SCD Package](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/Transform%20SCD%20Package.jpeg?raw=true)

- Customer & Territory Dimension Loads:
  ![Customer Package](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/dim_customer.jpeg?raw=true)
  ![Territory Package](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/dim_terrirtary.jpeg?raw=true)

---

## 🧾 Summary
This project illustrates the development of a professional-grade data warehouse using SSIS, with full ETL automation, auditing, and Power BI insights tailored for telecom operations.
