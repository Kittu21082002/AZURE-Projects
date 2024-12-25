# Fintech SQL Data Migration into Azure Portal

## Project Overview
This project involves migrating SQL data into the Azure ecosystem and processing it through multiple layers for structured data management. The architecture incorporates a Bronze-Silver-Gold data layer approach using Azure Synapse, PySpark, and Delta Tables.

## Tech Stack
- **Azure SQL Database**: Source database containing historical data.
- **Azure Synapse**: For creating and managing data pipelines.
- **Azure Data Lake Storage (ADLS)**: Storage for Bronze, Silver, and Gold layers.
- **PySpark**: Data transformation and processing.
- **Delta Tables**: Storing structured and optimized data in Silver and Gold layers.
- **SQL**: For defining database schema and queries.

---

## Project Workflow

### 1. Historical Data Preparation
- Created an Azure SQL Database with tables containing historical data.
- Inserted initial datasets into the database.

### 2. Data Pipeline Setup (SQL to Bronze)
- Created a pipeline in Azure Synapse to dynamically move data from SQL Database to the Bronze Layer in ADLS.
- Used a Copy Data activity in the pipeline for seamless data transfer.

### 3. Bronze to Silver Transformation
- Developed a PySpark notebook (`BronzeToSilverDataProcess.ipynb`) to:
  - Read raw data from the Bronze Layer.
  - Perform data cleaning and validation.
  - Write the processed data into the Silver Layer in Delta format.

### 4. Silver to Gold Transformation
- Created another PySpark notebook (`SilvertoGolddataproces.ipynb`) to:
  - Read cleaned data from the Silver Layer.
  - Perform business logic transformations (e.g., aggregations, joins).
  - Write the final structured data into the Gold Layer in Delta format.

### 5. Pipeline Automation
- Set up a pipeline (`Pipelineforfintech`) in Azure Synapse to automate:
  - Data movement from SQL to Bronze.
  - Execution of PySpark notebooks for Bronze → Silver and Silver → Gold transformations.
- Configured sequential execution and parameterized pipelines for flexibility.

---

## Setup Instructions

1. **Prepare the SQL Database:**
   - Use SQL scripts to create tables and insert historical data.

2. **Configure Azure Synapse:**
   - Create linked services for SQL Database and ADLS.
   - Define datasets for Bronze, Silver, and Gold layers.
   - Set up Synapse Pipelines for data extraction and movement.

3. **Develop PySpark Notebooks:**
   - Write and upload notebooks for Bronze-to-Silver and Silver-to-Gold transformations.
   - Test notebooks on Spark Pool.

4. **Automate Pipelines:**
   - Add pipeline activities to execute PySpark notebooks.
   - Configure triggers for scheduled execution.

5. **Validate End-to-End Workflow:**
   - Test the entire pipeline with sample data to ensure data accuracy and automation.

---

## Contributing

- Fork the repository.
- Create a new branch for your feature or bug fix.
- Commit and push changes to your branch.
- Submit a pull request for review.

---

## Key Learnings

- Practical experience with Azure Synapse and ADLS.
- Understanding of PySpark and Delta Tables for data transformation.
- Building end-to-end automated data pipelines.
- Best practices for handling large-scale data migration projects.

---

## Conclusion

This project demonstrates an effective approach to Fintech SQL data migration using Azure technologies. By leveraging PySpark, Delta Tables, and Synapse Pipelines, it provides a scalable and automated solution for managing and transforming large datasets. The structured workflow ensures data integrity and supports advanced analytics needs.

