# Understanding European Electricity Consumption and Spending Pipeline
ADS-508 AWS Cloud Computing Final Project

## Getting Started (in AWS):
1. In SageMaker Studio, open a new terminal and run the following code (line by line):
```
git init
git clone https://github.com/nlee98/ADS-508-AWS-Cloud-Computing.git
```
2. Execute the [Library-Dependencies-Setup Notebook](https://raw.githubusercontent.com/nlee98/ADS-508-AWS-Cloud-Computing/main/Library-Dependencies-Setup.ipynb)
3. Run the [ADS-508_Final_Notebook.ipynb](https://raw.githubusercontent.com/nlee98/ADS-508-AWS-Cloud-Computing/main/ADS-508_Final_Notebook.ipynb)

## AWS Tools Used:
* S3
* Athena/PyAthena
* SageMaker Image - DeepAR Built-In Algorithm (for model training)

## Repository Contents:
* [Setup - Jupyter Notebook](https://github.com/nlee98/ADS-508-AWS-Cloud-Computing/blob/main/Library-Dependencies-Setup.ipynb)
* [Project - Jupyter Notebook](https://github.com/nlee98/ADS-508-AWS-Cloud-Computing/blob/main/ADS-508_Final_Notebook.ipynb)
* [Data Field Descriptions](https://github.com/nlee98/ADS-508-AWS-Cloud-Computing/blob/main/Data_Field_Descriptions.ipynb)

## Project Notebook Sections:
- Libraries and Dependencies Import
- S3 Bucket Connection
- Data Source Copying (Copy Raw Data Sources from Public S3 Bucket to Personal S3 Bucket)
- Athena Database Connection
  - Create Tables in Athena Database
- Data Exploration via PyAthena Queries
  - Monthly Average Electricity Price
  - Average Hourly Electricity Price
- Pre-Processing
  - Data Ingestion via Pandas
    - Parse Datasets to the Same Time Frame
  - Identification and Imputation of Missing Values
  - Data Distribution Evaluation
  - Removal of Unnecessary Columns
  - Further Parsing of Datasets
    - Selection of Records, where _sistema_ = "HU"
    - Removal of Household Records Lacking Values for All Dates of Interest
    - Feature Creation
      - Create Month and Day_of_Week Columns from Date Value
      - Create a Daily Temp_range Column from Max_Temp and Min_Temp
    - Feature Transformation
      - Normalization of Numerical Features
    - Data Partitioning

## Data Sources:
The CSV files from each source were downloaded and uploaded to a public S3 bucket (s3://ads-508-spring2023-team3)
- [Hourly_European_Market_Data.csv](https://www.kaggle.com/datasets/thedevastator/hourly-european-power-market-prices)
- [London_Energy.csv](https://www.kaggle.com/datasets/emmanuelfwerr/london-homes-energy-data)
- [London_Weather.csv](https://www.kaggle.com/datasets/emmanuelfwerr/london-weather-data)
