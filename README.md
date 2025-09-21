# Python

🏥 Medicare Provider Data Pipeline (CMS API Project)
📌 Project Overview

This project demonstrates how to build a healthcare data engineering pipeline in Python using the CMS Provider Utilization & Payment Data API.
https://data.cms.gov/provider-data/dataset/27ea-46a8#api

The goal is to showcase real-world ETL workflows:
Extracting data from a public healthcare API
Validating provider identifiers (NPI)
Cleaning and splitting valid vs invalid data
Storing results in Google Drive for analysis and reporting

🔧 Tech Stack
Python 🐍 → requests, pandas
Data Validation → custom NPI validation (Luhn algorithm)
Storage → Google Drive (via Colab)
Output Formats → CSV for downstream analysis

🚀 Pipeline Steps
1️⃣ Extract Data from CMS API
Connected to the CMS Medicare Provider API
Used both GET (SQL-like queries) and POST JSON queries to retrieve data.
Loaded API results into a Pandas DataFrame for processing.

2️⃣ Validate Data Quality
Checked for missing values with df.isnull().sum() and created grouped reports.
Implemented a National Provider Identifier (NPI) validator:
Must be 10 digits long
Must pass the Luhn check digit algorithm

3️⃣ Split Valid vs Invalid Data
Providers with valid NPIs → stored in Facilities.csv
Providers with invalid NPIs → stored in Facilities_Exception.csv (with npi_valid flag)

4️⃣ Save Outputs to Google Drive
All files stored inside /MyDrive/HealthcareProjects/ folder:
✅ Facilities.csv → clean dataset for reporting
❌ Facilities_Exception.csv → audit file with invalid NPIs
