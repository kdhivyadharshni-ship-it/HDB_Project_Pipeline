# HDB Resale Flat Prices ETL Pipeline

## Overview

This project implements an end-to-end ETL (Extract, Transform, Load) pipeline for the HDB Resale Flat Prices dataset obtained from data.gov.sg.

The pipeline:
- Extracts HDB resale datasets from the Data.gov.sg API
- Combines all datasets into a master dataset
- Performs data cleaning and validation
- Removes invalid and duplicate records
- Applies business transformations
- Generates hashed identifiers
- Produces Raw, Cleaned, Transformed, Failed and Hashed datasets

The project also includes an AWS solution architecture for secure and scalable data ingestion and data exploitation.

---

## Technology Stack

- Python 3.x
- Pandas
- Requests
- Jupyter Notebook
- Git & GitHub
- AWS

---

## Prerequisites

Install Python 3.10 or later.

Install the required packages:

```bash
pip install -r requirements.txt
```

---

## Repository Contents

- `HDB_Project_Pipeline.ipynb` – ETL pipeline implementation
- `README.md` – Project documentation
- `requirements.txt` – Python dependencies
- `Pipeline_Architecture_HDB.pdf` – AWS solution architecture

---

## How to Run

1. Clone the repository.

```bash
git clone https://github.com/kdhivyadharshni-ship-it/HDB_Project_Pipeline.git
```

2. Navigate to the project folder.

```bash
cd HDB_Project_Pipeline
```

3. Install the required packages.

```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook.

```bash
jupyter notebook
```

5. Open **HDB_Project_Pipeline.ipynb** and run all cells.

---

## ETL Workflow

### Extract
- Download HDB resale datasets from Data.gov.sg.
- Combine all datasets into a master dataset.

### Clean
- Standardize column names.
- Validate and clean data.
- Remove invalid and duplicate records.

### Transform
- Calculate remaining lease.
- Calculate price per square metre.
- Extract transaction year and month.

### Load
Generate the following outputs:
- Raw
- Cleaned
- Transformed
- Failed
- Hashed

---

## Data Quality Rules

- Resale Price > 0
- Floor Area > 0
- Valid Lease Commencement Year
- Valid Transaction Month
- Duplicate records removed while keeping the highest resale price

---

## AWS Architecture

The repository includes an AWS architecture design covering:
- Data Ingestion
- Data Exploitation
- Security
- Scalability
- Performance

---

## Author

**Dhivyadharshni Karthikeyan**

Data Engineering Assessment – HDB Resale Flat Prices ETL Pipeline