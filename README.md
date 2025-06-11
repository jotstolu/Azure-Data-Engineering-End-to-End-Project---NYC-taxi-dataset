# Azure-Data-Engineering-End-to-End-Project---NYC-taxi-dataset
This End to End Project involves Data Ingestion, Data Storage, Data Processing / ETL Pipelines, Data Transformation & Cleaning, and Data Delivery. 
•	Bronze Layer: Raw data ingested directly from the website API stored in parquet format. 
The dataset for this project was extracted from NYC taxi limosine commision website - (https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). the greentaxi trip records which were in parquet format were extracted for january till december 2024
•	Silver Layer: Cleaned data, removing duplicates and handling missing values, ensuring it’s ready for analytics.
•	Gold Layer: Aggregated and enriched data tailored to specific business needs


# PROJECT ARCHITECTURE


## PHASE 1
1) PHASE 1
This phase involved data ingestion and storage from NYC taxi limosine commision website - (https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). the greentaxi trip records which were in parquet format were extracted for january till december 2024 using Azure data factory. A dynamic and parameterized data pipelines were orchestrated using activities such as for each activity, if condition, copy data activity to pull these data into the bronze container. 

