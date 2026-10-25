# E-commerce-Incremental-Data-Pipeline

## Project Overview

This project demonstrates an end-to-end data engineering pipeline built using **Azure Databricks, SQL Database, Delta Lake, Unity Catalog, and GitHub**. The pipeline extracts data from an external SQL database using Lakehouse Federation, processes it through the Medallion Architecture, maintains historical records using SCD Type 2, and generates business-level aggregations for reporting and analysis.

The project also incorporates incremental data processing, Databricks dashboards, alerts, job orchestration, and email notifications to demonstrate an automated and maintainable data engineering workflow.

## Architecture

The pipeline follows the Medallion Architecture, consisting of Bronze, Silver, and Gold layers.

**Data Flow:**

SQL Database → Lakehouse Federation → Bronze → Silver → Gold → Dashboards & Alerts

GitHub integration supports code versioning and collaboration, while Databricks Jobs orchestrate the pipeline execution.

## Technologies Used

- **Azure Databricks** – Data processing, transformation, and orchestration
- **SQL Database** – Source system for structured data
- **Lakehouse Federation** – Accessing data in the external SQL database
- **Delta Lake** – Reliable storage and data management
- **Unity Catalog** – Data governance and catalog management
- **PySpark and Spark SQL** – Data transformation and processing
- **GitHub** – Version control and collaborative development
- **Databricks AI/BI Dashboards** – Data visualization and reporting
- **Databricks Jobs and Alerts** – Workflow orchestration and notifications

## Project Implementation

### 1. Source Connectivity Using Lakehouse Federation

- Connected Azure Databricks to an external SQL database using Lakehouse Federation.
- Configured the required connection details and authentication credentials.
- Accessed source tables from Databricks for downstream data processing.

### 2. Bronze Layer – Raw Data Ingestion

- Ingested source data into the Bronze layer to maintain the raw data representation.
- Stored the ingested data in Delta tables for reliable downstream processing.
- Implemented incremental ingestion logic to process newly available or updated records rather than repeatedly processing the entire source dataset.

### 3. Silver Layer – Data Cleaning and Transformation

- Cleaned and standardized the ingested data.
- Handled data quality issues and transformed columns into appropriate formats.
- Performed data enrichment and joined relevant datasets.
- Implemented incremental processing to identify and process new or changed records.
- Applied SCD Type 2 logic to maintain historical versions of records and track changes over time.

### 4. Gold Layer – Business Transformations

- Applied business logic and aggregations to the cleaned Silver-layer data.
- Created Gold-layer tables containing business-ready datasets.
- Used incremental processing to update the Gold layer efficiently.
- Prepared aggregated data for reporting, dashboard development, and business analysis.

### 5. Historical Tracking Using SCD Type 2

- Implemented SCD Type 2 logic to preserve historical changes instead of overwriting existing records.
- Maintained validity timestamps to identify when each version became effective and when it ceased to be current.
- Used current-record indicators to distinguish active records from historical versions.

### 6. Unity Catalog and Delta Lake

- Organized and managed data assets using Unity Catalog.
- Used Delta tables across the Bronze, Silver, and Gold layers.
- Leveraged Delta Lake capabilities for reliable data storage and table operations.

### 7. GitHub Integration and Version Control

- Integrated GitHub with Azure Databricks Repos.
- Managed project code through version control.
- Pushed code changes to GitHub to maintain a centralized repository.
- Enabled team members to pull updated code and collaborate on development.

### 8. Dashboard Development and Alerts

- Developed four to five dashboards using Databricks' built-in dashboarding capabilities.
- Created visualizations using data from the Gold layer.
- Published dashboards for reporting and analysis.
- Configured an alert based on the total distinct order count.
- Set up email notifications and tested the alert using a customized email format.

### 9. Job Orchestration and Email Notifications

- Created a Databricks Job to orchestrate the end-to-end workflow.
- Configured tasks for the Bronze, Silver, and Gold processing stages.
- Integrated dashboard and alert-related steps into the workflow where supported by the configured job tasks.
- Triggered the job manually to validate the execution flow.
- Configured job notifications and verified the resulting emails.

## Key Features

- End-to-end data ingestion and transformation
- Lakehouse Federation for external SQL database connectivity
- Medallion Architecture using Bronze, Silver, and Gold layers
- Incremental data processing
- Data cleaning, enrichment, joins, and aggregations
- SCD Type 2 historical tracking
- Delta Lake storage and Unity Catalog governance
- GitHub-based version control and collaboration
- Databricks dashboards and configurable alerts
- Multi-task job orchestration and email notifications

## Project Outcome

This project demonstrates how to build and orchestrate a structured data engineering pipeline in Azure Databricks. It combines incremental ingestion, layered data transformation, historical data tracking, business aggregations, visualization, monitoring, and version control into a single workflow.

The resulting architecture provides a foundation for developing scalable, maintainable, and analytics-ready data pipelines.

