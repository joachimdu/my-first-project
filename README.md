# About my first project on GitHub
I am currently learning a basic data engineering learning roadmap and I am on week 9 out of a 16 week program.

For week 9, the focus is on cloud integration. Where I am supposed to extend my existing ETL pipeline by uploading my Parquet dataset into a cloud storage platform such as as AWS S3 or Google Cloud Storage (GCS)

By the end of the project, I should be able to:
1. Create and configure a cloud storage bucket
2. Setup IAM permissions or service accounts for secure access
3. Write a python script to upload Parquet files to the cloud
4. Validate that my data is correctly uploaded and accessible from the cloud console.

# Why this week matters

Up until now, I have been operating my data pipeline locally - fetching via API, transforming via Python and storing via PostgreSQL.

Week 9 transitions me to a cloud-based persistence, foundational for scalable data systems.

In production data engineering environments, data is stored in cloud object storage to ensure:
1. Scalability - can store millions of objects without local disk limitations
2. Durability - managed backups and replication
3. Interoperability - Enables downstream integration with Athena, BigQuery and Dashboards

This project bridges local ETL work with real-world cloud architecture.