# Databricks-ETL-Project

## Project Overview
This project demonstrates the creation and management of a Data Engineering pipeline using **Apache Spark** (via **PySpark**) on the **Databricks** platform. The project involves processing CSV files, extracting and transforming data, and loading the results into DBFS and Delta Tables.

## Goal
The main goal of this project is to implement an **ETL pipeline** for analyzing customer purchasing behavior, focusing on customers who bought **AirPods after purchasing an iPhone** or **only iPhone and AirPods**. The project includes:

1. **Extracting data** from CSV files stored in **DBFS** and Delta tables.
2. **Transforming data** using PySpark, including filtering and joining datasets based on specific business logic.
3. **Loading data** into DBFS and Delta tables.

## Files in this Repository
- **CSV Files**: Data sources used for the project.
  - `Products_Updated.csv`: Contains details about products.
  - `Transaction_Updated.csv`: Contains transaction data for customers.
  - `Customer_Updated.csv`: Contains customer information.

- **Python Notebooks**:
  - `apple_products_analysis.ipynb`: Main notebook that orchestrates the ETL process.
  - `extractor.ipynb`: Contains the code for data extraction.
  - `transform.ipynb`: Implements the transformation logic.
  - `loader.ipynb`: Handles the loading of the transformed data.
  - `loader_factory.ipynb`: Implements the factory design pattern for defining loading mechanisms.
  - `reader_factory.ipynb`: Implements the factory design pattern for different data sources (CSV, Parquet, Delta).

## Project Setup

### Prerequisites
- **Databricks Account**: You need access to a Databricks workspace.
- **Cluster**: A Databricks cluster should be created to run the notebooks.
- **Databricks File System (DBFS)**: Upload the CSV files to DBFS.

### Steps to Run the Project

1. **Upload Files to DBFS**:
   - Upload the `Products_Updated.csv`, `Transaction_Updated.csv`, and `Customer_Updated.csv` files to DBFS.

2. **Create Delta Tables**:
   - In Databricks, navigate to the **Catalog** > **Database Tables**.
   - Create a Delta table by uploading the `Customer_Updated.csv` file from DBFS and attaching a cluster.

3. **Execute the Notebooks**:
   - Open and run each of the notebooks in the following order:
     1. **`extractor.ipynb`**: Extract data from CSV files and Delta tables.
     2. **`transform.ipynb`**: Apply the transformation logic to identify specific customer purchase behaviors.
     3. **`loader.ipynb`**: Load the transformed data into DBFS and Delta tables.

4. **Run the Main Workflows**:
   - Open and run `apple_products_analysis.ipynb` to trigger the different ETL workflows.

## Transformation Logic
Two key transformations are implemented:
1. **AirPods after iPhone Purchase**: Identify customers who bought AirPods immediately after purchasing an iPhone.
2. **Only iPhone and AirPods**: Identify customers who only purchased iPhone and AirPods, with no other products.

## Data Storage
- **DBFS**: Data is stored in the Databricks File System for analysis.
- **Delta Tables**: Results are saved in Delta tables for optimized querying and ACID transactions.

## Credits
This project is inspired by the video of  [YouTube Channel "The Big Data Show"](https://www.youtube.com/@TheBigDataShow).

---

### Contact
For questions or suggestions, feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/manish-chamarajanagar-mahesh/).
