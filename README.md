# Microsoft Fabric NYC Taxi Data Project
This repository was created to share some personal projects that make up my portfolio as a Data Analyst and Analytics Engineer

![Fabric Architecture Excalidraw](https://github.com/user-attachments/assets/43ade0d2-52cc-4fc3-a295-41e41d2d622a)


End-to-End Data Analytics Project using Microsoft Fabric
Overview
This document provides a step-by-step guide to implementing an End-to-End Data Analytics solution using Microsoft Fabric. It is tailored for Data Analysts and BI/Data Engineers to streamline the data analytics process while leveraging Microsoft Fabric's capabilities.

Personas
Data Analyst: Responsible for analyzing and interpreting data to provide actionable insights.
BI/Data Engineer: Focused on designing and building scalable data pipelines and infrastructure for data processing.
Pre-requisites
To successfully implement the solution, the following pre-requisites are required:

Fabric Account: Access to Microsoft Fabric for project implementation.
SQL (Basic Knowledge): Fundamental understanding of SQL for data querying and manipulation.
Data Warehousing (Basic Knowledge): Familiarity with data storage principles, table structures, and schema designs.
Data Pipelines (Basic Knowledge): Knowledge of data flow processes, transformations, and automation.

ETL Process
Metadata Management
A metadata table named processing_log is created to store information about the data processed, ensuring traceability and accountability for every load cycle.
Staging Layer Operations
Data Deletion: Prior to any new data load, all existing data in the staging layer is cleared to avoid duplication or inconsistencies.
Data Load: New data is loaded into the staging layer after the cleanup process.
Presentation Layer Operations
Data Append: Data from the staging layer is appended to the presentation layer table. This step ensures that the presentation layer remains up-to-date with the latest processed data.

![image](https://github.com/user-attachments/assets/76b5ea82-0940-4bfc-8ab3-c83ebb4fe1f1)


Dynamic workflow to upload monthly data
![image](https://github.com/user-attachments/assets/0638ca8e-cb58-4e93-b953-bf4e2b6c7e4a)

