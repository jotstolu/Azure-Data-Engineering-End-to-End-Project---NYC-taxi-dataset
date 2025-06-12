# Azure-Data-Engineering-End-to-End-Project - NYC-taxi-dataset
This repository showcases a complete data engineering workflow on Azure for the NYC Green Taxi dataset:

- **Bronze Layer**: Ingest raw Parquet files from the NYC TLC API into the bronze container  
- **Silver Layer**: Clean, dedupe, and enrich with PySpark in Databricks  
- **Gold Layer**: Transformed data was saved in delta format
 

# PROJECT ARCHITECTURE
![image](https://private-user-images.githubusercontent.com/121890747/454069538-4d61cc70-315d-4162-8374-5dd476e4e5ae.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDk3MDI0MDksIm5iZiI6MTc0OTcwMjEwOSwicGF0aCI6Ii8xMjE4OTA3NDcvNDU0MDY5NTM4LTRkNjFjYzcwLTMxNWQtNDE2Mi04Mzc0LTVkZDQ3NmU0ZTVhZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNjEyJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDYxMlQwNDIxNDlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01OGVmMzAzMjg4MzQyYzMyYTg4OTQ0NjY1NGNlNTUyNGFiMjhkYTdjYjhkZjRiMjA0NThlODE1NmJjODRlMGUzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.Vk6OulmIzPgOOw5r5mcTRvMUkCFGOfOrOFp7CXFtbRs)


### Phase 1: Bronze (Raw Ingestion)

- **Source**  
  - NYC TLC Green Taxi trip records (Parquet) for Jan–Dec 2024  
  - Data extracted via Azure Data Factory from HTTP API into ADLS Gen2

- **Orchestration**  
  - Parameterized ADF pipelines: **Copy Data**, **ForEach**, **If Condition**  
  
- **Storage**  
  - Raw data stored in `bronze/` container as parquet files

### Phase 2: Silver (Cleansing & Enrichment)

- **Compute**  
  - Azure Databricks PySpark notebooks

- **Transformations**  
  - Schema enforcement and type casting  
  - Split and normalize multi‑valued fields (e.g., payment types)  
  - Remove duplicate records; filter out bad mileage/fare entries  
  - Impute or drop nulls based on domain rules

- **Output**  
  - Cleaned, enriched tables in `silver/` container

### Phase 3: Gold (Quality & Aggregation)  
  - Stored in `gold/` Delta tables, ready for BI tools

---
## Technology Stack

| Component                   | Purpose                                         |
| --------------------------- | ----------------------------------------------- |
| Azure Data Factory (ADF)    | Data ingestion & orchestration                  |
| Azure Data Lake Storage Gen2| Scalable storage for Delta tables               |
| Azure Databricks            | Spark ETL, Delta Live Tables, Workflows         |
| Delta Lake                  | ACID‑compliant, performant data format          |
| PySpark                     | Transformation logic                            |







