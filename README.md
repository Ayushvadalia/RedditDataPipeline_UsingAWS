# Reddit Data Pipeline 🚀

## Introduction
This project implements a scalable data pipeline to extract, process, and analyze Reddit data using modern tools like **Apache Airflow**, **Celery**, and AWS services including **S3**, **Glue**, **Athena**, and **Redshift**. It is designed for efficient data ingestion, transformation, and querying while providing room for real-time analytics and insights.

---

## Pipeline Overview

### **Architecture Highlights**
- **Source**: Reddit API serves as the primary data source.
- **Orchestration**: Apache Airflow manages the workflow and task scheduling.
- **Task Distribution**: Celery handles distributed task execution for concurrent subreddit data fetching.
- **Data Storage**:
  - **Postgres**: Tracks pipeline execution logs and task statuses.
  - **Amazon S3**: Stores raw and processed data for scalability and reliability.
- **Data Transformation and Querying**:
  - **AWS Glue**: Organizes and prepares data for analysis.
  - **Amazon Athena/Redshift**: Facilitates data querying and advanced analytics.

---

## How It Works

### **1. Fetching Reddit Data**
- The **Reddit API** is accessed via Airflow using secure credentials stored in environment variables.
- Subreddits are defined dynamically in the workflow configuration for flexibility.

### **2. Orchestration and Task Management**
- **Airflow** triggers the pipeline, breaking it into independent tasks such as subreddit data collection and storage.
- Tasks are queued and distributed to **Celery** workers for parallel execution.

### **3. Storage and Transformation**
- Raw data fetched by workers is saved in **Amazon S3**.
- **AWS Glue** performs ETL (Extract, Transform, Load) operations, converting unstructured data into analyzable formats.

### **4. Analysis and Insights**
- Query the data using **Amazon Athena** for immediate insights or load it into **Redshift** for complex queries and dashboards.

---

## Features
- **Parallel Processing**: Leverages Celery for fetching data from multiple subreddits simultaneously.
- **Cloud Integration**: AWS services ensure scalability and cost-effectiveness.
- **Error Logging**: Postgres logs task statuses for traceability and debugging.
- **Modular Design**: Each component is independently containerized for ease of deployment and maintenance.

---

## Getting Started

### **Prerequisites**
- Docker
- Python 3.x
- Apache Airflow
- Celery
- AWS Account with S3, Glue, Athena, and Redshift configured

### **Setup Guide**

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-friend/Reddit_Data_Pipeline.git
   cd Reddit_Data_Pipeline

### **Reddit_Data_Pipeline**:
```bash
├── dags/                    # Airflow workflows (DAGs)
├── workers/                 # Celery workers for parallel task execution
├── postgres/                # Database setup for task logging
├── s3/                      # S3 integration for storage
├── docker-compose.yml       # Orchestration script for Docker containers
├── requirements.txt         # Python dependencies
└── .env                     # Environment variables



