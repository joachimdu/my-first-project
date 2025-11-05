# ☁️ Week 9 Project Overview – Cloud Storage Integration
# 🎯 Objective

This week marks the start of your Cloud Integration phase. You’ll extend your existing ETL pipeline by uploading your Parquet dataset into a cloud storage platform such as AWS S3 or Google Cloud Storage (GCS).

By the end of this project, you will:

Create and configure a cloud storage bucket.

Set up IAM permissions or service accounts for secure access.

Write a Python script to upload Parquet files to the cloud.

Validate that your data is correctly uploaded and accessible from the cloud console.

# 🧩 Why This Week Matters

Up until now, your data pipeline has operated locally — fetching, transforming, and storing data in a local PostgreSQL database. Week 9 transitions you to cloud-based persistence, a foundational skill for scalable data systems.

In production data engineering environments, data is stored in cloud object storage to ensure:

Scalability: Can store millions of objects without local disk limitations.

Durability: Managed backups and replication.

Interoperability: Enables downstream integration with Athena, BigQuery, and dashboards.

This project bridges your local ETL work with real-world cloud architecture.

# ⚙️ Core Skills and Concepts
Skill / Concept	Description
Cloud Storage Fundamentals	Understanding buckets, objects, and storage classes
IAM Roles & Credentials	Configuring least-privilege access to cloud resources
SDK Usage (boto3 / google-cloud-storage)	Using Python SDKs to programmatically upload files
Secure Credential Management	Storing keys safely using environment variables or .env files
ETL Extension	Adding a cloud upload stage as the final step of your ETL process
# 🧠 Project Tasks
Step 1 – Cloud Setup

For AWS: Create an S3 bucket via console and generate access keys.

For GCP: Create a Cloud Storage bucket and generate a service account JSON key.

Store credentials securely using .env file or environment variables.

Step 2 – Install SDK
pip install boto3        # for AWS
## or
pip install google-cloud-storage   # for GCP

Step 3 – Write Upload Script
import os
import boto3

# Initialize S3 client
s3 = boto3.client(
    "s3",
    aws_access_key_id=os.getenv("AWS_ACCESS_KEY_ID"),
    aws_secret_access_key=os.getenv("AWS_SECRET_ACCESS_KEY")
)

# Upload file
s3.upload_file("data/weather_data.parquet", "my-weather-bucket", "weather_data.parquet")
print("✅ Upload successful!")

Step 4 – Integrate with ETL Pipeline

Modify your existing Prefect flow or standalone ETL script to include a “Upload to Cloud” task.

Implement logging to record upload status (success/failure).

Optionally, use Prefect retries for transient network errors.

Step 5 – Validate Upload

Log in to your cloud console (AWS S3 / GCP Storage).

Confirm the uploaded file appears in the bucket.

Optionally, test downloading it back to confirm accessibility.

# 🧰 Example Folder Structure
data_pipeline/
├─ etl/
│  ├─ extract_transform_load.py
│  ├─ upload_to_cloud.py
│  └─ prefect_flow.py
├─ data/
│  └─ weather_data.parquet
├─ logs/
│  └─ upload.log
└─ .env

# 📈 Deliverables
Deliverable	Description
✅ Cloud Bucket	Accessible bucket in AWS S3 or GCP Cloud Storage
✅ Upload Script	Python script to upload Parquet files
✅ Integrated ETL Flow	Prefect flow includes cloud upload stage
✅ Log File	Captures upload results and timestamps
✅ Screenshot Proof	Cloud console view of uploaded file
🔗 Resources
Topic	Link
AWS Boto3 Guide	https://boto3.amazonaws.com/v1/documentation/api/latest/guide/s3-example-creating-buckets.html

GCP Storage Python Client	https://cloud.google.com/storage/docs/reference/libraries

IAM Best Practices	https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html

Python dotenv	https://saurabh-kumar.com/python-dotenv/
# 🔄 Week 8 → Week 9 Transition
From Week 8	To Week 9
Local orchestration with Prefect	Cloud integration and storage
ETL stored locally in PostgreSQL	ETL output persisted in cloud
Task retries and scheduling	Data persistence and cloud connectivity

# 📘 Template Version: Week 9 – Data Engineering Roadmap Project Overview