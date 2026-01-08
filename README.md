# End-to-End-Data-Engineering-Pipeline-Project
This project demonstrates an end-to-end big data pipeline where GitHub Archive data is ingested, processed using Apache Spark on AWS EMR, and loaded into Amazon Redshift for analytical querying.

## Architecture Flow
Local System → Amazon S3 → AWS EMR (Spark) → Temporary S3 Location → Amazon Redshift
### Step 1: EMR Cluster Creation
Created an AWS EMR cluster with Hadoop and Apache Spark, configuring instance types, IAM roles, and security groups. 
<img width="1920" height="1080" alt="Screenshot 2026-01-08 194243" src="https://github.com/user-attachments/assets/b2bf5efc-d269-4ed5-9943-5de5aa730c79" />

