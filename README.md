# Sparkify Cloud Data Warehouse (Snowflake + AWS)

## 📖 Project Overview
This project is a cloud-based data warehousing solution built for the fictional music streaming company **Sparkify**.  
The goal was to design and implement a **multi-layered data architecture** using **Snowflake** and **AWS S3** to process, clean, and transform semi-structured JSON data into an **analytics-ready star schema**.

---

## Objective
To create a scalable and secure **data warehouse** that:
- Ingests raw JSON data from **AWS S3**
- Transforms and cleans data using Snowflake SQL
- Implements a **Bronze → Silver → Gold** layered approach
- Enables fast analytical queries through a **star schema**

---

## Architecture Overview
**Data Flow:** AWS S3 → Snowflake Stages → Snowflake Tables (Bronze → Silver → Gold)

- **Bronze (Raw Layer):** Stores unprocessed JSON data from S3  
- **Silver (Staging Layer):** Cleans, flattens, and filters semi-structured data  
- **Gold (Analytics Layer):** Contains the star schema for analytical workloads  

This architecture allows for clear data separation, easier maintenance, and scalability for future data pipelines.

---

## Tools & Technologies
- **Snowflake** – Cloud data warehouse for transformation and analytics  
- **AWS S3** – Cloud storage for raw JSON data  
- **IAM Roles & Stages** – Secure integration between AWS and Snowflake  
- **SQL** – For cleaning, transformation, and schema modeling  

---

## Implementation Summary
1. **Data Ingestion:**  
   Raw `song_data` and `log_data` JSON files were stored in AWS S3 and securely accessed in Snowflake using IAM roles and external stages.

2. **Data Staging:**  
   The JSON data was parsed, flattened, and cleaned in the staging layer to prepare for transformation.

3. **Data Transformation:**  
   Data was joined, filtered (e.g., only “NextSong” events), and standardized to remove duplicates and null values.

4. **Star Schema Design:**  
   - **Fact Table:** `fact_songplays`  
   - **Dimension Tables:** `dim_users`, `dim_songs`, `dim_artists`, `dim_time`  
   This schema supports analytical queries like user activity, song popularity, and artist performance.

5. **Validation & Analysis:**  
   Data quality checks were performed using aggregate and distinct queries to ensure accuracy and completeness.

---

## Key Learnings
- Integrating **AWS S3 with Snowflake** using IAM-based security  
- Applying the **Bronze–Silver–Gold** data modeling pattern  
- Transforming **semi-structured JSON** into relational models  
- Building and optimizing a **star schema** for analytical workloads  
- Strengthening understanding of **ETL processes and data warehousing best practices**

---

## Final Schema
- **Fact Table:** `fact_songplays`  
- **Dimension Tables:** `dim_users`, `dim_songs`, `dim_artists`, `dim_time`

---


## Tags
`#DataEngineering` `#Snowflake` `#AWS` `#ETL` `#SQL` `#CloudDataWarehouse` `#Analytics`
