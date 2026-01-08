# End-to-End-Data-Engineering-Pipeline-Project
This project demonstrates an end-to-end big data pipeline where GitHub Archive data is ingested, processed using Apache Spark on AWS EMR, and loaded into Amazon Redshift for analytical querying.

## Architecture Flow
Local System → Amazon S3 → AWS EMR (Spark) → Temporary S3 Location → Amazon Redshift
### Step 1: EMR Cluster Creation
Created an AWS EMR cluster with Hadoop and Apache Spark, configuring instance types, IAM roles, and security groups. 
<img width="1920" height="1080" alt="Screenshot 2026-01-08 194243" src="https://github.com/user-attachments/assets/b2bf5efc-d269-4ed5-9943-5de5aa730c79" />
### Step 2: Remote Development Setup
Connected VS Code to the EMR master node using the Remote Development (SSH) extension for seamless Spark development.  
<img width="1920" height="1080" alt="Screenshot 2026-01-08 194730" src="https://github.com/user-attachments/assets/85c6fae9-9a6a-4551-97d8-e98caf582ad6" />
<img width="1920" height="1080" alt="Screenshot 2026-01-08 192757" src="https://github.com/user-attachments/assets/5bdff78d-4ab0-4894-a2cd-5e2d9b6fc97a" />
### Step 3: Download GH Archive Data
Downloaded GitHub Archive (`.json.gz`) event files to the local system for ingestion.
<img width="1920" height="1080" alt="Screenshot 2026-01-08 192909" src="https://github.com/user-attachments/assets/8f227bbc-d511-4ea5-bbda-01396192f878" />
<img width="1920" height="1080" alt="Screenshot 2026-01-08 192942" src="https://github.com/user-attachments/assets/796c457a-e1a4-4d0b-b057-242281342105" />
### Step 4: Upload Data to S3
Uploaded raw GH Archive files to Amazon S3 using AWS CLI for centralized data storage.
<img width="1920" height="1080" alt="Screenshot 2026-01-08 193001" src="https://github.com/user-attachments/assets/4a18d6f3-c74f-4a90-a6f3-0eaa7de96a68" />
### Step 5: Read Data using Spark
Used PySpark on EMR to read raw JSON data from S3 into Spark DataFrames.
### Step 6: Data Transformation
Cleaned, parsed, and transformed the GitHub event data using Spark SQL and DataFrame APIs.  
<img width="1920" height="1080" alt="Screenshot 2026-01-08 193200" src="https://github.com/user-attachments/assets/de3b4f22-2af6-44e1-b028-d4520c723260" />
### Step 7: Write Transformed Data to Temp S3
Stored the transformed data in a temporary S3 location in Parquet format for optimized loading.  
<img width="1920" height="1080" alt="Screenshot 2026-01-07 201315" src="https://github.com/user-attachments/assets/d6fe6687-5966-48ba-ab48-6c6a70555f67" />
### Step 8: Redshift Serverless Setup (Workgroup & Namespace)
Created an Amazon Redshift Serverless namespace and workgroup to manage database resources and compute independently.  
<img width="1920" height="1080" alt="Screenshot 2026-01-07 084647" src="https://github.com/user-attachments/assets/d8518ab1-01fc-4873-8d35-a591742021e7" />
### Step 9: Redshift Table Creation
Created target tables in Amazon Redshift Query Editor based on the transformed schema.  
<img width="1920" height="1080" alt="Screenshot 2026-01-08 193033" src="https://github.com/user-attachments/assets/6d114de6-d86f-4ced-ba90-42804c9b0198" />
### Step 10: Load Data into Redshift using Spark
Loaded data into Amazon Redshift directly from Spark using JDBC without executing a manual COPY command.  
<img width="1920" height="1080" alt="Screenshot 2026-01-08 193219" src="https://github.com/user-attachments/assets/f0016516-c6c8-480a-853e-b85eb3f34c15" />
<img width="1920" height="1080" alt="Screenshot 2026-01-08 200546" src="https://github.com/user-attachments/assets/16eb224d-01ce-4f96-be30-a887bc797cbb" />
### Step 11: Data Validation
Validated the loaded data by running analytical queries in Amazon Redshift.  
![WhatsApp Image 2026-01-08 at 8 43 29 PM](https://github.com/user-attachments/assets/df82fe9f-be8e-4523-b79b-0335ce2ab977)

