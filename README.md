HDB Resale Flat Prices ETL Pipeline
Project Overview
This project implements an end-to-end ETL (Extract, Transform, Load) pipeline for the HDB Resale Flat
Prices dataset published on data.gov.sg.
The pipeline extracts multiple HDB resale datasets using the Data.gov.sg API, combines them into a master
dataset, performs data validation and cleansing, removes invalid and duplicate records, applies business
transformations, generates hashed identifiers, and exports the processed datasets into separate output
folders.
The solution also includes AWS architecture designs for secure and scalable data ingestion and data
exploitation.
Technology Stack
• 
• 
• 
• 
• 
• 
Python 3.10+
Pandas
Requests
Jupyter Notebook
AWS Architecture (Design)
Git & GitHub

Prerequisites
Before running the project, ensure the following are installed:
• 
• 
• 
Python 3.10 or later
pip (Python Package Manager)
Jupyter Notebook (optional)
Install the required Python packages:
pip install-r requirements.txt
or
pip install pandas requests notebook jupyter
How to Run
1. 
Clone the repository.
git clone https://github.com/<your-github-username>/HDB_Project_Pipeline.git
1. 
Navigate to the project folder.
2
cd HDB_Project_Pipeline
1. 
Install the dependencies.
pip install-r requirements.txt
1. 
Launch Jupyter Notebook.
jupyter notebook
1. 
2. 
Open HDB_Project_Pipeline.ipynb.
Execute all notebook cells from top to bottom.
ETL Workflow
Extract
• 
• 
• 
• 
Retrieve HDB Resale Flat Price datasets from Data.gov.sg.
Download all child datasets.
Store each dataset in the raw_data folder.
Combine all datasets into a single master dataset.
Transform
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
Load
Standardize column names.
Convert data types.
Trim and normalize text values.
Validate mandatory fields.
Remove invalid records.
Remove duplicate records while keeping the highest resale price.
Calculate remaining lease.
Generate additional analytical columns such as:
Price per square metre
Transaction year
Transaction month
Generate the following outputs:
• 
• 
• 
raw_data/ – Raw downloaded datasets and consolidated master dataset.
cleaned/ – Records that pass all validation rules.
transformed/ – Business-ready dataset with derived columns.
3
• 
• 
failed/ – Invalid and duplicate records.
hashed/ – Cleaned dataset with SHA-256 hashed identifiers.
Data Quality Rules
The pipeline performs the following validations:
• 
• 
• 
• 
• 
Resale price must be greater than zero.
Floor area must be greater than zero.
Lease commencement year must be valid.
Transaction month must be valid.
Duplicate business records are removed while retaining the highest resale price.
Security Considerations
The accompanying AWS architecture incorporates:
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
Private VPC
NAT Gateway
AWS Glue
Amazon S3
Glue Data Catalog
Amazon Athena
AWS PrivateLink (VPC Endpoint)
IAM Roles
AWS KMS Encryption
Amazon CloudWatch
AWS CloudTrail
Repository Contents
• 
• 
• 
• 
• 
ETL Pipeline Notebook
README
requirements.txt
AWS Architecture Diagrams
Generated Output Files
Future Improvements
• 
• 
Configuration-driven ETL
Logging framework
4
• 
• 
• 
• 
Automated scheduling using AWS Glue Jobs
Incremental data ingestion
Unit testing
CI/CD integration using GitHub Actions
Author
Dhivyadharshni Karthikeyan
Data Engineering Assessment – HDB Resale Flat Prices ETL Pipeline
5