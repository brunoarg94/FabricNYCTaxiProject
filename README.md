# Microsoft Fabric NYC Taxi Data Project

1. Project Architecture
The image below illustrates the overall architecture of the NYC Taxi Data Project. This architecture outlines the key components and the data flow, from collection to visualization.

![Fabric Architecture Excalidraw](https://github.com/user-attachments/assets/43ade0d2-52cc-4fc3-a295-41e41d2d622a)


End-to-End Data Analytics Project using Microsoft Fabric

- Fabric Data Pipeline: Manages orchestration as well as the ingestion, transformation, and loading of data into a Fabric Lakehouse.
- Fabric Lakehouse: Serves as a storage repository for raw data and files.
- Power BI: Connects to the Lakehouse using Direct Lake to create a near real-time dashboard.

2. General Project Description
This dashboard is a data monitoring and analytics solution designed to provide a high-level summary of taxi rides in NYC within a specific date range. It captures, transforms, and presents key metrics to offer actionable insights into passenger behavior, trip details, and operational performance. The dashboard enables stakeholders to understand ride patterns, detect potential issues, and optimize the user experience.

3. ETL Process (Data Pipelines) phases

Metadata Management
A metadata table named processing_log is created to store information about the data processed, ensuring traceability and accountability for every load cycle.

Staging Layer Operations
Data Deletion: Prior to any new data load, all existing data in the staging layer is cleared to avoid duplication or inconsistencies.

Data Load
New data is loaded into the staging layer after the cleanup process.

Presentation Layer Operations
Data Append: Data from the staging layer is appended to the presentation layer table. This step ensures that the presentation layer remains up-to-date with the latest processed data.

Data Dictionary
Target table `nyctaxi_yellow` data dictionary (Presentation Layer) detailing the structure and meaning of each field in the dataset.

| **Field Name**          | **Description**                                                                  | **Data Type**         | **Example Value**                |
|-------------------------|----------------------------------------------------------------------------------|-----------------------|----------------------------------|
| `do_borough`            | Borough where the drop-off occurred.                                             | Text/String           | "Manhattan"                      |
| `do_zone`               | Specific zone within the borough for drop-off.                                   | Text/String           | "Upper West Side"                |
| `passenger_count`       | Number of passengers in the taxi during the ride.                                | Numeric (Integer)     | 2                                |
| `payment_method`        | Method of payment used for the ride (e.g., cash, credit card).                   | Text/String           | "Credit Card"                    |
| `pu_borough`            | Borough where the pickup occurred.                                               | Text/String           | "Brooklyn"                       |
| `pu_zone`               | Specific zone within the borough for pickup.                                     | Text/String           | "Downtown Brooklyn"              |
| `total_rides`           | Total count of rides (aggregated metric).                                        | Numeric (Integer)     | 13,000,000                       |
| `total_amount`          | Total fare amount collected for the ride, including tips and fees.               | Numeric (Decimal)     | 53.25                            |
| `tpep_dropoff_datetime` | Date and time when the ride ended.                                               | DateTime              | "2024-01-01 15:30:00"            |
| `tpep_pickup_datetime`  | Date and time when the ride started.                                             | DateTime              | "2024-01-01 15:00:00"            |
| `trip_distance`         | Total distance traveled during the ride (e.g., in miles or kilometers).          | Numeric (Decimal)     | 5.2                              |
| `vendor`                | Name of the vendor providing the service (e.g., taxi company).                   | Text/String           | "Creative Mobile Technologies"   |

4. Data Visualization (Power BI)
Tool: Power BI
Purpose: Create interactive dashboards for visualizing:

- Number of trips by passenger.
- Most common payment methods.
- Vendors with the highest volume of rides.
- Trends in trip distance, passenger count, and revenue over time.

Import mode: Direct Lake
https://learn.microsoft.com/en-us/fabric/get-started/direct-lake-overview

5. Project Benefits

- Near Real-Time Monitoring: Continuously updated data enables agile decision-making.
- Operational Optimization: Insights can be used to enhance user experience and operational efficiency.
- Flexibility and Scalability: The modular architecture supports future expansions and adjustments.

5. Final Considerations
The NYC Taxi Data Project is a robust solution for capturing, transforming, and analyzing taxi ride data. By leveraging modern tools available in Microsoft Fabric, this project ensures efficiency and scalability, meeting the needs of transportation data monitoring and analysis.


