# 🏠 Zillow Real Estate Data Analytics ETL Pipeline

This project demonstrates a complete **end-to-end ETL pipeline** that extracts real estate data from **Zillow’s RapidAPI**, transforms and loads it into an **Amazon Redshift** data warehouse, and finally visualizes it using **Amazon QuickSight**.

---

## 📌 Project Highlights

- 🔄 **ETL Orchestration** with Apache **Airflow**
- ☁️ **AWS Services** used: EC2, S3, Lambda, Redshift, IAM, QuickSight
- 📡 **Data Source**: Zillow (via [RapidAPI](https://rapidapi.com))
- 🤖 Automated using Airflow DAGs and AWS Lambda functions
- 📊 Interactive dashboard built on Amazon QuickSight

---

## 📂 Project Architecture

```text
1. Extract:
   - Python script pulls real estate data from Zillow RapidAPI.
   - Data is stored as JSON and uploaded to S3 (Landing Zone).

2. Transform:
   - AWS Lambda copies JSON to a new bucket and converts it to CSV.
   - CSV is stored in a processed S3 bucket.

3. Load:
   - CSV data is loaded into Amazon Redshift using COPY commands.
   - Airflow DAG monitors each step using S3 sensors and triggers.

4. Visualize:
   - Redshift tables are connected to Amazon QuickSight for dashboarding.
```
# 🛠️ Tech Stack

| Component          | Technology               |
|--------------------|--------------------------|
| API Source         | Zillow via RapidAPI      |
| Workflow Engine    | Apache Airflow           |
| Compute            | AWS EC2                  |
| Storage            | Amazon S3                |
| Processing         | AWS Lambda               |
| Data Warehouse     | Amazon Redshift          |
| Visualization      | Amazon QuickSight        |
| Language           | Python                   |

# 🚀 End-to-End Workflow

## Data Extraction
- Python script fetches real estate listings from Zillow's RapidAPI
- JSON data is saved locally and uploaded to an S3 bucket

## Data Transformation
- AWS Lambda function is triggered when a new JSON is uploaded
- Transforms the JSON into a CSV file and stores it in another S3 bucket

## Data Loading
- Apache Airflow DAG waits for the transformed CSV in S3
- Data is loaded into Redshift using the COPY command

## Visualization
- Data in Redshift is connected to Amazon QuickSight
- Dashboards are created for business insights

# 🧪 Setup Instructions

## 🔐 1. API Key (Zillow)
1. Sign up on RapidAPI
2. Subscribe to the Zillow API and get your API key

## 🖥️ 2. EC2 Environment
1. Launch an EC2 instance (Ubuntu recommended)
2. Install Python, Apache Airflow, AWS CLI, and boto3
3. Clone this repository and configure the DAGs

## ☁️ 3. S3 Buckets
Create the following S3 buckets:
- `zillow-raw-data`
- `zillow-staged-data`
- `zillow-transformed-data`

## 🔄 4. AWS Lambda
Deploy two Lambda functions:
1. `copy_raw_to_stage`: Moves raw JSON to a staging bucket
2. `transform_json_to_csv`: Converts JSON to CSV and stores it in the final bucket

## 🧱 5. Redshift
1. Set up a Redshift cluster
2. Create necessary tables using SQL schema provided
3. Ensure IAM roles and bucket permissions are configured for COPY

## 📊 6. QuickSight
1. Connect Redshift as a data source
2. Build visualizations for metrics like:
   - Top cities by listings
   - Average property prices
   - Monthly trends in real estate listings

# 📁 Directory Structure
.  
├── dags/  
│ └── zillow_etl_dag.py  
├── lambda/  
│ ├── copy_raw_to_stage.py  
│ └── transform_json_to_csv.py  
├── scripts/  
│ └── extract_zillow_data.py  
├── redshift/  
│ └── create_tables.sql  
├── dashboard/  
│ └── quicksight_screenshots/  
├── requirements.txt


# 📸 Sample Dashboard (Amazon QuickSight)
Insert dashboard screenshots here to show data insights and visualizations.

# 🧠 Key Learnings
- How to orchestrate an ETL workflow using Apache Airflow
- Leveraging AWS Lambda for serverless data processing
- Automating data pipelines using S3 event triggers and Airflow DAGs
- Building insightful dashboards with Amazon QuickSight
- Integrating multiple AWS services in a production-grade pipeline

# 🛡️ Prerequisites
- AWS account with necessary permissions (IAM roles, S3, Lambda, Redshift, QuickSight)
- RapidAPI account
- Python 3.8+
- Airflow 2.x


# 💬 Contact
📧 Email: nandinirathod909@gmail.com  
🔗 LinkedIn: [Nandini Rathod](https://github.com/Nandini2233)
