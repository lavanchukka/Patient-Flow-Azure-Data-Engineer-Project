# Helathcare-End-to-End-Azure-Data-Engineer-Project
In this project we'll create real time healthcare patient data pipeline as data source and use various services like Azure Eventhubs, Azure Databricks, Delta lake and synapse analytics. also, implement medallion architecture, schema evolution and create facts and dimension tables and connect the cleaned and transformed data to PowerBI.
Real-Time Patient Flow Analytics on Azure
Azure PySpark Azure Data Factory Azure Synapse Python Databricks PowerBI Git

📑 Table of Contents
📌 Project Overview
🎯 Objectives
📂 Project Structure
🛠️ Tools & Technologies
📐 Data Architecture
⭐ Star Schema Design
⚙️ Step-by-Step Implementation
1. Event Hub Setup
2. Data Simulation
3. Storage Setup
4. Databricks Processing
5. Synapse SQL Pool
6. Version Control
📊 Data Analytics
✅ Key Outcomes
📜 License
📌 Project Overview
This project demonstrates a real-time data engineering pipeline for healthcare, designed to analyze patient flow across hospital departments using Azure cloud services.
The pipeline ingests streaming data, processes it in Databricks (PySpark), and stores it in Azure Synapse SQL Pool for analytics and visualization.

Part 1 – Data Engineering: Build the real-time ingestion + transformation pipeline.
Part 2 – Analytics: Connect Synapse to Power BI and design an interactive dashboard for hospital KPIs.

For a full Youtube Tutorial of this project click this Part-1 link/Part-2 link.

Pipeline
Architecture
🎯 Objectives
Collect real-time patient data via Azure Event Hub.
Process and cleanse data using Databricks (Bronze → Silver → Gold layers).
Implement a star schema in Synapse SQL Pool for efficient querying.
Enable Version Control with Git.
📂 Project Structure
real-time-patient-flow-azure/
│
├── databricks-notebooks/  # Transformation notebooks
│   ├── 01_bronze_rawdata.py
│   ├── 02_silver_cleandata.py
│   └── 03_gold_transform.py
├── simulator/             # Data simulation scripts
│   └── patient_flow_generator.py
├── sqlpool-quries/        # SQL scripts for Synapse
│   └── SQL_pool_quries.sql
├── git_commands/                  # Git Commands
└── README.md              # Project documentation
🛠️ Tools & Technologies
Azure Event Hub – Real-time data ingestion
Azure Databricks – PySpark-based ETL processing
Azure Data Lake Storage – Staging raw and curated data
Azure Synapse SQL Pool – Data warehouse for analytics
Power BI – Dashboarding (future step)
Python 3.9+ – Core programming
Git – Version control
📐 Data Architecture
The pipeline follows a multi-layered architecture:

Bronze Layer: Raw JSON data from Event Hub stored in ADLS.
Silver Layer: Cleaned and structured data (validated types, null handling).
Gold Layer: Aggregated and transformed data ready for BI consumption.
⭐ Star Schema Design
The Gold layer data in Synapse follows a star schema for optimized analytics:

Fact Table: FactPatientFlow (patient visits, timestamps, wait times, discharge)
Dimension Tables:
DimDepartment – Department details
DimPatient – Patient demographic info
DimTime – Date and time dimension
⚙️ Step-by-Step Implementation
1. Event Hub Setup
Created Event Hub namespace and patient-flow hub.
Configured consumer groups for Databricks streaming.
2. Data Simulation
Developed Python script patient_flow_generator.py to stream fake patient data (departments, wait time, discharge status) to Event Hub.
Producer Code
3. Storage Setup
Configured Azure Data Lake Storage (ADLS Gen2).
Created containers for bronze, silver, and gold layers.
4. Databricks Processing
Notebook 1: Reads Event Hub stream into Bronze.
Notebook 2: Cleans and validates schema.
Notebook 3 : Aggregates and prepares star schema tables.
5. Synapse SQL Pool
Created dedicated SQL Pool.
Executed schema and fact/dimension creation queries from:
DDL_Qureis
6. Version Control
Version control with Git:
Commands reference
📊 Data Analytics
Once the data pipeline was established and a Star Schema implemented in Synapse SQL Pool, the next step was to build an interactive dashboard in Power BI.

🔗 Synapse → Power BI Connection
Connected Azure Synapse SQL Pool to Power BI using a direct SQL connection.
Imported FactPatientFlow and Dimension tables.
Established relationships for Star Schema-based reporting.
📈 Dashboard Features
The Healthcare Patient Flow Dashboard provides insights into:

Bed Occupancy Rate by department and gender.
Patient Flow Trends (admissions, wait times).
Department-Level KPIs (length of stay, Total Patients).
Interactive Filters & Slicers for gender.
Screenshot 2025-08-30 155951
✅ Key Outcomes
End-to-End Pipeline: From real-time ingestion → transformation → warehouse → analytics.
Scalable Architecture: Easily adaptable for different hospital datasets.
Business Insights: Hospital admins can monitor bed usage, patient flow, and department efficiency in real time.
Portfolio Value: Demonstrates both Data Engineering and Analytics skills in one project.
