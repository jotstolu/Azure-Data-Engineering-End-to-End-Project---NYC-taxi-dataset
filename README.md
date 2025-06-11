# Azure-Data-Engineering-End-to-End-Project - NYC-taxi-dataset
This End to End Project involves Data Ingestion, Data Storage, Data Processing / ETL Pipelines, Data Transformation & Cleaning, and Data Delivery. this project makes use of the medallion architecture
•	Bronze Layer: Raw data ingested directly from the website API stored in parquet format. 
The dataset for this project was extracted from NYC taxi limosine commision website - (https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). the greentaxi trip records which were in parquet format were extracted for january till december 2024
•	Silver Layer: Cleaned data, removing duplicates and handling missing values, ensuring it’s ready for analytics.
•	Gold Layer: Aggregated and enriched data tailored to specific business needs


# PROJECT ARCHITECTURE
![project_Archictecture](https://private-user-images.githubusercontent.com/121890747/454069538-4d61cc70-315d-4162-8374-5dd476e4e5ae.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDk2NjkzNDQsIm5iZiI6MTc0OTY2OTA0NCwicGF0aCI6Ii8xMjE4OTA3NDcvNDU0MDY5NTM4LTRkNjFjYzcwLTMxNWQtNDE2Mi04Mzc0LTVkZDQ3NmU0ZTVhZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNjExJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDYxMVQxOTEwNDRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02NDRmZmNlOTE0ZDMwY2Q5ZTI5MWU0NmM4NTNmODcyZGQ3ZDNmYzE5OGJkNTYzMmYxMGIwNDE5NjkxYTcwZTIyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.2at4u4weXt5ee50qVz4tCZcs5MA6h_tCbN9d8NjdjQE)



## **1) PHASE 1**
This phase involved data ingestion and storage from NYC taxi limosine commision website - (https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). the greentaxi trip records which were in parquet format were extracted for january till december 2024 using Azure data factory. A dynamic and parameterized data pipelines were orchestrated using activities such as for each activity, if condition, copy data activity to pull these data into the bronze container. 

## **2) PHASE 2**
This phase involved data transformation such as splitting of column, defining the schema, removing invalid values, casting of datatypes etc. pyspark was used as a transformation tools on microsoft Azure Databrick workspace. 

## **3) PHASE 3**
The data from the transfomed layer were saved as delta format into the gold layer

