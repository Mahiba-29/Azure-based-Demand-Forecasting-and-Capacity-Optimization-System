# Azure-based-Demand-Forecasting-and-Capacity-Optimization-System

This project implements an end-to-end cloud-based forecasting system designed to predict Azure Compute and Storage demand. The workflow integrates multi-cloud data ingestion, scalable storage, advanced feature engineering, machine learning model training, and Power BI–based visualization to support Azure’s capacity planning and supply chain decision-making.

1. Data Sources
The solution brings together data from three major platforms:
- Snowflake DB – provides structured enterprise usage and infrastructure data.
- Google Cloud Platform (GCP) – supplies external cloud usage signals and demand indicators.
- Render API – provides API-level real-time consumption metrics.
These diverse sources create a rich dataset combining internal and external demand drivers.

2. Data Ingestion Layer
All incoming data is ingested through:

✔ Azure Data Factory (ADF)
+ Automates ingestion workflows
+ Connects securely to Snowflake, GCP, and API endpoints
+ Handles scheduling, pipelines, and logging

✔ Azure Data Lake Storage (ADLS)
+ Acts as the centralized raw data storage location
+ Stores data in hierarchical folders for easy integration with Databricks
This ensures scalable, fault-tolerant data handling capable of growing with Azure’s infrastructure signals.
