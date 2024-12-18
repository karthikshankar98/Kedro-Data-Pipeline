# Data Pipeline using Kedro framework

## Overview
This project processes and validates medical datasets related to Lupus patients. The pipeline cleans, merges, and validates data to produce a unified dataset.

## Requirements
- Python 3.8 or higher
- Kedro 0.19.10
- Dependencies listed in `requirements.txt`

1. Clone the repository:
   ```bash
   git clone https://github.com/karthikshankar98/Kedro-Data-Pipeline.git
   cd Kedro-Data-Pipeline

2. Create a virtual environment:
   ```bash
   python -m venv env
   env\Scripts\activate (for linux/macOS - source env/bin/activate)

3. Install dependencies (might take about 3-4 mins):
   ```bash
   pip install -r requirements.txt

4. Run the pipeline from the project root directory:
   ```bash
   kedro run

## Outputs:
- data/02_staging/century_health.db : contains 5 individual processed tables for the datasets, a .py file is attached in the same folder to query .db file
- data/03_master_data.master_data.csv : which is essentially the merged dataset
- data/04_validation/master_data_validation.json : data validation output generated by Great Expectations

## Key Files
src/century_health_pipeline/pipeline/data_engineering_CH/nodes.py: Contains data cleaning and transformation logic
src/century_health_pipeline/pipeline/data_engineering_CH/pipeline.py: Defines the Kedro pipeline structure

src/century_health_pipeline/pipeline/data_engineering_CH/validation.py: Implements validation checks using Great Expectations
great_expectations/expectations/master_data_expectations.json: Basic validation rules for the master data

conf/base/catalog.yml: Data catalog file

notebooks/Data_Assessment_&_Analysis.ipynb: Jupyter notebook containing code for data assessment and analysis

