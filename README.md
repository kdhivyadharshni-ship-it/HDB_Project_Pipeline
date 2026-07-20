# HDB Resale Flat Prices ETL Pipeline

## Overview

This project implements an end-to-end ETL (Extract, Transform, Load) pipeline for the HDB Resale Flat Prices dataset obtained from data.gov.sg.

The pipeline performs the following:

- Extracts multiple HDB resale datasets using the Data.gov.sg API
- Combines all datasets into a master dataset
- Performs data cleaning and validation
- Removes invalid and duplicate records
- Applies business transformations
- Generates hashed identifiers
- Produces separate output datasets for Raw, Cleaned, Transformed, Failed and Hashed data

The project also includes AWS solution architecture designs for Data Ingestion and Data Exploitation.

---

# Technology Stack

- Python 3.x
- Pandas
- Requests
- Jupyter Notebook
- Git & GitHub
- AWS Architecture (Solution Design)

---

# Prerequisites

Install Python 3.10 or later.

Install the required Python packages:

```bash
pip install -r requirements.txt
```

or

```bash
pip install pandas requests notebook
```

---

# Project Structure

```
HDB_Project/
│
├── HDB_Project_Pipeline.ipynb
├── README.md
├── requirements.txt
│
├── raw_data/
│   ├── hdb_file_1.csv
│   ├── hdb_file_2.csv
│   ├── hdb_file_3.csv
│   ├── hdb_file_4.csv
│   ├── hdb_file_5.csv
│   └── master_hdb_dataset.csv
│
├── cleaned/
│   └── cleaned_dataset.csv
│
├── transformed/
│   └── transformed_dataset.csv
│
├── failed/
│   └── failed_dataset.csv
│
├── hashed/
│   └── hashed_dataset.csv
│
└── architecture/
    ├── Data_Ingestion_Architecture.png
    └── Data_Exploitation_Architecture.png
```

---

# How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/<your-github-username>/HDB_Project_Pipeline.git
```

### 2. Navigate to the Project

```bash
cd HDB_Project_Pipeline
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Execute the Notebook

Open **HDB_Project_Pipeline.ipynb** and run all cells from top to bottom.

---

# ETL Workflow

## Extract

- Retrieve HDB resale datasets from Data.gov.sg API
- Download all child datasets
- Store each dataset in the **raw_data** folder
- Combine into a master dataset

## Clean

- Standardize column names
- Convert data types
- Trim text fields
- Validate mandatory fields
- Remove invalid records
- Remove duplicate records

## Transform

Generate additional business columns:

- Remaining Lease
- Price per Square Metre
- Transaction Year
- Transaction Month

## Load

Generate the following datasets:

- Raw
- Cleaned
- Transformed
- Failed
- Hashed

---

# Data Quality Rules

The pipeline validates:

- Resale Price > 0
- Floor Area > 0
- Valid Lease Commencement Year
- Valid Transaction Month
- Duplicate business records are removed while retaining the highest resale price

---

# Output Files

| Folder | Description |
|---------|-------------|
| raw_data | Raw datasets downloaded from Data.gov.sg |
| cleaned | Records that passed validation |
| transformed | Business-ready transformed dataset |
| failed | Invalid and duplicate records |
| hashed | Cleaned dataset with SHA-256 hashed identifier |

---

# AWS Architecture

The solution includes two architecture designs:

### Data Ingestion

- Data.gov.sg
- NAT Gateway
- AWS Glue
- Amazon S3
- Glue Data Catalog

### Data Exploitation

- Tableau
- Amazon Athena
- AWS PrivateLink
- Amazon S3
- Glue Data Catalog

The architecture has been designed with the following considerations:

- Security
- Scalability
- Performance
- Private networking
- Data encryption

---

# Future Enhancements

- Incremental Data Loading
- Logging Framework
- Configuration File Support
- AWS Glue Job Scheduling
- CI/CD Pipeline
- Unit Testing

---

# Author

Dhivyadharshni Karthikeyan

Data Engineering Assessment – HDB Resale Flat Prices ETL Pipeline