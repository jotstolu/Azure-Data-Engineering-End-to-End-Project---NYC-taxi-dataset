# Azure-Data-Engineering-End-to-End-Project - NYC-taxi-dataset
This repository showcases a complete data engineering workflow on Azure for the NYC Green Taxi dataset:

- **Bronze Layer**: Ingest raw Parquet files from the NYC TLC API into the bronze container  
- **Silver Layer**: Clean, dedupe, and enrich with PySpark in Databricks  
- **Gold Layer**: Transformed data was saved in delta format
 

# PROJECT ARCHITECTURE
![image](https://github.com/jotstolu/Azure-Data-Engineering-End-to-End-Project---NYC-taxi-dataset/blob/main/image/NYC%20taxi%20project%20architecture.png?raw=true)


### Phase 1: Bronze (Raw Ingestion)

- **Source**  
  - [NYC TLC Green Taxi trip records (Parquet) for Jan–Dec 2024](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
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







