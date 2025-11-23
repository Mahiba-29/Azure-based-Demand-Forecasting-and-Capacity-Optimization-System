# Azure-based-Demand-Forecasting-and-Capacity-Optimization-System

This project implements an end-to-end cloud-based forecasting system designed to predict Azure Compute and Storage demand. The workflow integrates multi-cloud data ingestion, scalable storage, advanced feature engineering, machine learning model training, and Power BI–based visualization to support Azure’s capacity planning and supply chain decision-making.
<img width="1000" height="342" alt="image" src="https://github.com/user-attachments/assets/64ef7ff5-cff4-4b21-813b-b647acbd11e2" />


**1. Data Sources**
   
The solution brings together data from three major platforms:
- Snowflake DB – provides structured enterprise usage and infrastructure data.
- Google Cloud Platform (GCP) – supplies external cloud usage signals and demand indicators.
- Render API – provides API-level real-time consumption metrics.
These diverse sources create a rich dataset combining internal and external demand drivers.

**2. Data Ingestion Layer**
   
All incoming data is ingested through:

✔ Azure Data Factory (ADF)
+ Automates ingestion workflows
+ Connects securely to Snowflake, GCP, and API endpoints
+ Handles scheduling, pipelines, and logging

✔ Azure Data Lake Storage (ADLS)
+ Acts as the centralized raw data storage location
+ Stores data in hierarchical folders for easy integration with Databricks
This ensures scalable, fault-tolerant data handling capable of growing with Azure’s infrastructure signals.

**3. Data Processing Layer (Azure Databricks)**

Azure Databricks is the core data processing and ML environment in this architecture.

✔ Bronze Layer (Raw Data)
+ Stores unprocessed data exactly as received
+ Maintains full data lineage and fidelity

✔ Silver Layer (Clean + Enriched Data)
+ Data cleaning applied
+ Feature engineering performed (lags, moving averages, seasonality, growth, economic indicators, etc.)
+ Time-series alignment and normalization

✔ Gold Layer (Model-Ready Data)
+ Final curated dataset
+ Used for machine learning and dashboard consumption

This multi-layered Lakehouse approach ensures clean, high-quality, reliable input for modeling.

**4. Machine Learning Model Training**

The Model Training block uses Databricks ML runtime to build multiple forecasting models:
+ Random Forest Regressor
+ XGBoost Regressor
+ Prophet
+ ARIMA (Auto-ARIMA)

Each model is trained on engineered features from the Silver/Gold layers.

Model	Accuracy-
Random Forest: 	97.69% (Best),
      XGBoost:    97.47%,
        ARIMA:    84.2%,
      Prophet: 	84.19%

Random Forest performed the best due to its ability to learn complex patterns from multiple correlated signals.

The final outputs include:
+ Predicted Compute demand
+ Predicted Storage demand
+ Weekly and monthly trend insights
+ Model performance metrics (MAE, RMSE, SMAPE)

**5. Visualization Layer (Power BI)**

The final forecasts and performance metrics are published to Power BI, enabling:
+ Real-time interactive dashboards
+ Demand trend reports
+ Regional and service-level breakdowns
+ Capacity planning insights
+ Model accuracy monitoring

