# SSIS-Package
# 🏬 Stores Data Warehouse

## 📘 Overview
This project showcases the entire lifecycle of developing a data warehouse solution, from initial design to final implementation:

- Data Modeling
- ETL (Extract, Transform, Load) using SSIS
- Historical tracking with Slowly Changing Dimensions (SCD)
- Interactive dashboarding with Power BI

The solution was developed using:

- **SQL Server** for database management
- **SSIS** for data extraction, transformation, and loading (ETL)
- **Power BI** for data visualization

---

## ⭐ Key Highlights

### 🛠️ Database Restoration & Setup
- Restored source database files into SQL Server.
- Prepared the development environment for building the data warehouse.

### 🧱 Data Warehouse Design
- Created **Fact** and **Dimension** tables following the Star Schema model.
- Tables include:
  - **Dimension Tables**: `DimProduct`, `DimCustomer`, `DimTerritory`, `DimDate`
  - **Fact Table**: `FactSales`
- Implemented **Slowly Changing Dimensions (SCD Type 2)** to preserve historical accuracy.

### 🔄 Slowly Changing Dimension (SCD) Implementation
SCD Type 2 tracks historical changes in dimension data. It allows querying both current and historical views of data.

Key attributes used:
- `StartDate`: Date when the record became effective.
- `EndDate`: Date when the record was no longer active (default: 9999-12-31 if still current).
- `IsCurrent`: Boolean flag indicating whether the record is active.

**SCD Workflow**:
1. **Compare incoming data with current records**.
2. **Mark the existing record as inactive** (`EndDate = GETDATE()`, `IsCurrent = 0`) if changes are detected.
3. **Insert a new version of the record** with updated values and `IsCurrent = 1`.

This ensures that each historical version of the record is preserved, maintaining full auditability.

### ⚙️ ETL Development using SSIS
- Created individual SSIS packages for loading each table:
  - `DimProduct`, `DimCustomer`, `DimTerritory`, `DimDate`, `FactSales`
- Incorporated SCD logic into the dimension ETL packages.

### 📈 Data Visualization with Power BI
- Developed interactive dashboards to analyze `FactSales` data.
- Enabled real-time business insights and data-driven decision-making.

---

## 🎯 Purpose
The data warehouse integrates information from multiple sources into a centralized repository, enabling unified reporting and analytics across the organization.

---

## 🧰 Tools Used
- SQL Server
- SSIS (SQL Server Integration Services)
- Power BI
- Power Query

---

## 🗺️ Data Warehouse Schema Diagram

![Data Warehouse Diagram](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/Diagram.jpg?raw=true)

---

## 🛠️ Project Workflow

1. **Download & Restore Source Files** into SQL Server.
2. **Design the Warehouse Schema** and determine suitable data types.
3. **Create Tables** with appropriate SCD tracking columns:
   - `StartDate`, `EndDate`, `IsCurrent`
4. **Develop ETL Packages**:
   - Load `DimProduct` and `DimCustomer` with change detection.
     ![Dim Product Package](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/dim_product.jpeg?raw=true)
   - Apply SCD logic:
     ![SCD Package](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/Transform%20SCD%20Package.jpeg?raw=true)
   - Load `DimTerritory`:
     ![Dim Territory](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/dim_terrirtary.jpeg?raw=true)
   - Load `DimDate`:
     ![Dim Date](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/dim_date.jpeg?raw=true)
   - Load `FactSales`:
     ![Fact Sales Package_full_load](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/fact_table.jpeg?raw=true)
   - Incremental_Load `FactSales`:
     ![Fact Sales Package_Incremental_Load ](https://github.com/Marwamedha/SSIS-Package/blob/main/ETL_Package/Load.png)

---

## 📌 Summary
This project showcases core concepts of modern data warehousing using SQL Server and SSIS, with practical implementation of SCD Type 2 and professional reporting via Power BI.
