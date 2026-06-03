# Cloud Data Warehouse on AWS Redshift

## Project Overview
This project builds a cloud-based data warehouse for Sparkify, a music streaming startup. The goal is to move raw song and user activity data from Amazon S3 into Amazon Redshift and create an analytics-ready database for business queries.

## Objective
The main objective is to design and implement an ETL pipeline that:
- Loads raw JSON data from S3 into Redshift staging tables
- Transforms staging data into a star schema
- Supports analytical queries on user listening behavior

## Technologies Used
- Python
- SQL
- Amazon S3
- Amazon Redshift
- AWS IAM
- ETL Pipelines
- Data Warehousing
- Star Schema Design

## Data Model

### Staging Tables
- `staging_events`
- `staging_songs`

### Fact Table
- `songplays`

### Dimension Tables
- `users`
- `songs`
- `artists`
- `time`

## Project Files
- `create_tables.py` - Drops and creates Redshift tables
- `etl.py` - Loads data from S3 into staging tables and inserts into analytics tables
- `sql_queries.py` - Contains SQL queries for table creation, copy commands, and inserts
- `dwh.cfg` - Stores configuration details for Redshift and S3

## ETL Pipeline
1. Read raw song and event data from Amazon S3.
2. Load data into Redshift staging tables.
3. Transform staging data into fact and dimension tables.
4. Run analytical queries on the final star schema.

## How to Run
1. Create an AWS Redshift cluster.
2. Update `dwh.cfg` with Redshift and IAM role details.
3. Run:
   ```bash
   python create_tables.py
