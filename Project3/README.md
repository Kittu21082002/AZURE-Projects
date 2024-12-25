# NYC Taxi Data Engineering Project

## Project Overview
This project demonstrates an end-to-end data engineering solution leveraging Azure Data Factory, Databricks, and Power BI. It involves ingesting NYC Taxi dataset dynamically via APIs, transforming the data using Medallion Architecture (Bronze, Silver, and Gold layers), and visualizing insights through Power BI.

### Key Features
- **Dynamic pipelines in Azure Data Factory** for data ingestion.
- **Data transformations using PySpark and Delta Lake** in Databricks.
- **Medallion architecture implementation** (Bronze, Silver, Gold layers).
- **Integration of Delta Tables with Power BI** for visualization.
- **Secure data handling with managed identities.**

---

## Project Flow
1. **Data Ingestion**:
   - Use Azure Data Factory (ADF) to dynamically fetch NYC Taxi data via APIs.
   - Store raw data in Parquet format in the **Bronze Layer**.

2. **Data Transformation**:
   - Process raw data in Databricks using PySpark.
   - Apply transformations to clean and structure the data.
   - Store processed data in the **Silver Layer** (still in Parquet format).

3. **Data Modeling**:
   - Use Delta Lake to create versioned Delta Tables in the **Gold Layer**.
   - Implement advanced features like time travel and Delta logs.

4. **Data Visualization**:
   - Connect Databricks Delta Tables to Power BI using Partner Connect.
   - Load data into Power BI to create reports and dashboards.

5. **Security**:
   - Implement managed identities in Azure to ensure secure access to data sources.

---

## Setup Instructions

### Prerequisites
- A computer with a stable internet connection.
- Azure account (create a free account if you don’t have one).
- Databricks workspace setup in Azure.
- Power BI Desktop installed.

### Step 1: Set Up Azure Data Factory
1. Create an **Azure Data Factory** instance.
2. Add a **linked service** for Azure Data Lake Storage (ADLS).
3. Configure the **pipeline** to:
   - Fetch data dynamically from the API using parameters.
   - Handle conditional logic (e.g., formatting month numbers).

### Step 2: Configure Databricks
1. Create a **Databricks workspace** in Azure.
2. Upload the provided notebooks:
   - `silver_notebook.dbc`: Handles transformations for the Silver Layer.
   - `gold_notebook.dbc`: Handles Delta Table creation in the Gold Layer.
3. Create a cluster and attach the notebooks.
4. Run the notebooks sequentially to process the data.

### Step 3: Establish Power BI Connection
1. Open **Databricks Partner Connect** in your workspace.
2. Select **Microsoft Power BI** and download the connection file.
3. Open the file in Power BI Desktop.
4. Authenticate using your Databricks access token:
   - Go to **Settings > Developer > Access Tokens** in Databricks.
   - Generate a new token and use it in Power BI.

### Step 4: Build Reports
1. Load Delta Tables from the Gold Layer into Power BI.
2. Create visualizations and dashboards as required.

---
## Key Learning Outcomes
- Build and manage dynamic data pipelines.
- Perform advanced data transformations using PySpark and Delta Lake.
- Implement industry-standard Medallion Architecture.
- Integrate with BI tools like Power BI for analytics.

---
## Conclusion

This project provides a complete data engineering workflow, from data ingestion to visualization, using modern tools and technologies like Azure Data Factory, Databricks, and Power BI. By implementing dynamic pipelines, Medallion architecture, and secure data handling, this project ensures scalability and readiness for real-world scenarios. Completing this project not only demonstrates your technical proficiency but also prepares you to tackle complex challenges in data engineering roles.