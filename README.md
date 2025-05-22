![image](https://github.com/user-attachments/assets/d395dab1-0a6f-41e6-88d5-8486647dfb9b)# Azure-Based-Cloud-Visualization-for-UK-Traffic-Accident-Analysis
A Business Intelligence (BI) and data engineering project focused on analyzing traffic accidents in the UK using Microsoft Azure cloud technologies. This project leverages Azure Functions, Blob Storage, Azure SQL Database, and Power BI to deliver a scalable, automated, and visual analytics solution.

## 📊 Project Overview

This project addresses the need for scalable and real-time insights into UK traffic accidents from 2010 to 2015. It implements a modern data lakehouse architecture and Business Intelligence workflows using Microsoft Azure. Key outcomes include data pipelines, a centralized data warehouse, and interactive dashboards for stakeholders.

## 🎯 Objectives

- Build a cloud-based data warehouse on Microsoft Azure
- Implement automated ETL pipelines using Azure Functions
- Provide real-time insights via Power BI dashboards
- Support data-driven decisions for improving UK road safety

## 📁 Dataset

- **Source:** UK Department for Transport (2010–2015)
- **Size:** ~876,000 records with 32 attributes
- **Content:** Accident severity, location, time, weather, road conditions, police attendance, etc.

## 🧱 Architecture

- **Ingestion Layer (Bronze):** Raw data uploaded to Azure Blob Storage using AzCopy and PowerShell scripts scheduled with Windows Task Scheduler.
- **Processing Layer (Silver):** Cleaned and transformed data via Azure Functions using C# and CsvHelper.
- **Analytics Layer (Gold):** Star schema implemented in Azure SQL Database, optimized for BI queries.
- **Visualization:** Interactive Power BI dashboards connected to the gold layer.

## 🧪 Technologies Used

| Category                    | Tools & Services                              |
|----------------------------|-----------------------------------------------|
| Data Ingestion             | AzCopy, PowerShell, Azure Blob Storage       |
| ETL                        | Azure Functions, CsvHelper, SqlBulkCopy      |
| Storage                    | Azure SQL Database                            |
| Orchestration & Automation | Task Scheduler, Azure Function Triggers      |
| Monitoring & Alerts        | SendGrid, ILogger                             |
| Visualization              | Power BI                                      |

## 📌 Key KPIs

- **Total Accidents:** COUNT of all accident events
- **Total Fatalities:** SUM of casualties where severity = fatal
- **Serious Accident Rate (SAR):** Serious/Fatal over Total Accidents
- **Average Speed Limit (AVGSpeed):** Mean of speed limits

## 📊 Dashboards

- **Page 1 – Accident Overview:**
  ![Image](https://github.com/user-attachments/assets/6d049c12-368a-4750-a7be-30b1722b4bab) 
- **Page 2 – Uncontrollable Causes:**
  ![Image](https://github.com/user-attachments/assets/acfff184-fef8-4c90-b355-2ef7e1eeee88)
- **Page 3 – Controllable Causes:** 
  ![Image](https://github.com/user-attachments/assets/7c4d511f-8714-48b7-a043-ebb8f1323209)
## 📐 Data Model

A star schema with the following structure:

- **Fact Table:** `Fact_Accidents`
- **Dimension Tables:** `Dim_Date`, `Dim_Time`, `Dim_LightConditions`, `Dim_WeatherConditions`, `Dim_RoadType`, `Dim_Police`, `Dim_AccidentSeverity`, `Dim_RoadSurfaceConditions`, `Dim_UrbanOrRuralArea`

## 🧪 ETL Workflow

1. **Upload Data:** Scheduled upload via AzCopy and PowerShell to Blob Storage.
2. **Raw to Bronze:** Triggered ingestion into Blob Storage (CSV).
3. **Bronze to Silver:** Clean and transform using Azure Functions.
4. **Silver to Gold:** Load structured star schema into Azure SQL Database.
5. **Power BI Integration:** Connect to gold layer and build dashboards.

## 📈 Results

- Efficient, automated, scalable BI pipeline
- Real-time insights into traffic safety
- Data-driven support for policy and infrastructure planning

## 📚 References

- Microsoft Learn & Azure Docs
- UK Department for Transport Datasets
- Kimball & Inmon Data Warehouse Methodologies
