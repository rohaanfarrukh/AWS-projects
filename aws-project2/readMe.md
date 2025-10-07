# 🚀 AWS Data Engineering ETL Pipeline (S3 + Glue + PySpark)

## 📌 Project Overview
This project demonstrates a complete **data engineering ETL pipeline** built using **AWS Glue** and **PySpark**.  
It reads raw CSV data from **Amazon S3**, cleans and transforms it in **AWS Glue**, and writes the processed data back to **S3**.

This pipeline automates data cleaning and prepares data for analytics or further processing.

---

## 🧠 Architecture
S3 (Raw Data)
↓
AWS Glue Crawler → AWS Glue Data Catalog (Schema)
↓
AWS Glue ETL Job (PySpark Script)
↓
S3 (Cleaned Data)

---


---

## ⚙️ Tools & Services Used
- **AWS S3** – Source & destination data storage
- **AWS Glue Crawler** – Automatically detect schema from CSV
- **AWS Glue Data Catalog** – Stores table metadata
- **AWS Glue Job (PySpark)** – Transform and clean data
- **AWS IAM** – Role permissions for Glue to access S3
- **PySpark** – Transformation logic (drop nulls, clean data)

---

## 🧰 Steps Implemented

1. **Uploaded Raw Data**  
   - `sales_data.csv` uploaded to S3 bucket: `rohaan-etl-input`

2. **Created Glue Crawler**  
   - Crawled the S3 path  
   - Created database: `etl_db`  
   - Created table: `rohaan_etl_input`

3. **Created Glue ETL Job**  
   - Type: Spark Script (Python)  
   - Script reads from Glue Catalog and cleans data

4. **ETL Script Logic:**
   ```python
   datasource = glueContext.create_dynamic_frame.from_catalog(
       database = "etl_db",
       table_name = "rohaan_etl_input"
   )

   cleaned_data = datasource.drop_null_fields()

   glueContext.write_dynamic_frame.from_options(
       frame = cleaned_data,
       connection_type = "s3",
       connection_options = {"path": "s3://rohaan-etl-output/cleaned_data/"},
       format = "csv"
   )
  
Fixed Permissions

Attached AmazonS3FullAccess to IAM role AWSGlueServiceRole-rohaan

Ran ETL Job Successfully

Output written to s3://rohaan-etl-output/cleaned_data/

Verified Output

Downloaded and viewed cleaned CSV (no nulls)

📊 Results

✅ Cleaned dataset stored in S3
✅ Null values removed
✅ Schema inferred automatically via Glue Catalog

🧠 Key Skills Demonstrated

-Data Engineering (ETL)
-AWS Glue (PySpark)
-S3 Data Lake Architecture
-IAM Role Configuration
-Data Cleaning
-Cloud Automation

