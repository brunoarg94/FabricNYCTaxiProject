# Microsoft Fabric NYC Taxi Data Project

## Overview

The **NYC Taxi Data Project** is an end-to-end data analytics solution leveraging Microsoft Fabric to monitor and analyze taxi rides in New York City. This project captures, processes, and visualizes key metrics, offering actionable insights into passenger behavior, trip details, and operational performance.

---

## 1. Project Architecture

The image below illustrates the architecture of the NYC Taxi Data Project, detailing the data flow from collection to visualization.

![Fabric Architecture Excalidraw](https://github.com/user-attachments/assets/43ade0d2-52cc-4fc3-a295-41e41d2d622a)

### Key Components:

- **Fabric Data Pipeline**: Orchestrates data ingestion, transformation, and loading into the Fabric Lakehouse.
- **Fabric Lakehouse**: Central repository for raw data and files.
- **Power BI**: Connects to the Lakehouse via Direct Lake to enable near real-time dashboards.

---

## 2. General Project Description

This solution provides a comprehensive dashboard to analyze taxi rides in NYC for a specific date range. The dashboard empowers stakeholders by:

- Monitoring ride patterns and passenger behaviors.
- Identifying operational bottlenecks.
- Supporting data-driven decision-making.

---

## 3. ETL Process (Data Pipelines)

### **Metadata Management**
A metadata table, `processing_log`, ensures traceability and accountability for all load cycles.

### **Staging Layer Operations**
- **Data Deletion**: Clears the staging layer before each new data load to avoid duplication or inconsistencies.
- **Data Load**: Loads new data into the staging layer.

### **Presentation Layer Operations**
- **Data Append**: Consolidates staging data into the presentation layer to maintain up-to-date insights.

---

## 4. Data Dictionary

The table below describes the fields in the `nyctaxi_yellow` dataset within the presentation layer:

| **Field Name**          | **Description**                                                     | **Data Type**         | **Example Value**                |
|-------------------------|---------------------------------------------------------------------|-----------------------|----------------------------------|
| `do_borough`            | Borough where the drop-off occurred.                                | Text/String           | "Manhattan"                      |
| `do_zone`               | Specific zone within the borough for drop-off.                      | Text/String           | "Upper West Side"                |
| `passenger_count`       | Number of passengers in the taxi during the ride.                   | Numeric (Integer)     | 2                                |
| `payment_method`        | Payment method used (e.g., cash, credit card).                      | Text/String           | "Credit Card"                    |
| `pu_borough`            | Borough where the pickup occurred.                                  | Text/String           | "Brooklyn"                       |
| `pu_zone`               | Specific zone within the borough for pickup.                        | Text/String           | "Downtown Brooklyn"              |
| `total_rides`           | Aggregated metric of total rides.                                   | Numeric (Integer)     | 13,000,000                       |
| `total_amount`          | Total fare amount (including tips and fees) in US dolar.            | Numeric (Decimal)     | 53.25                            |
| `tpep_dropoff_datetime` | Date and time when the ride ended.                                  | DateTime              | "2024-01-01 15:30:00"            |
| `tpep_pickup_datetime`  | Date and time when the ride started.                                | DateTime              | "2024-01-01 15:00:00"            |
| `trip_distance`         | Total distance traveled during the ride in miles.                   | Numeric (Decimal)     | 5.2                              |
| `vendor`                | Vendor providing the service (e.g., taxi company).                  | Text/String           | "Creative Mobile Technologies"   |

---

## 5. Data Visualization (Power BI)

### Tool: **Power BI**

#### **Key Features:**
- **Interactive Dashboards**: Visualize trends in trip counts, revenue, and distance.
- **Insights Provided**:
  - Number of trips by passenger.
  - Most common payment methods.
  - Top vendors by ride volume.
  - Geospatial analysis.


---

## 6. Project Benefits

- **Near Real-Time Monitoring**: Provides continuously updated data for agile decision-making.
- **Operational Optimization**: Identifies areas to improve efficiency and user experience.
- **Scalability**: Modular architecture supports future enhancements and expansions.

---

## 7. Final Considerations

The **NYC Taxi Data Project** demonstrates the power of Microsoft Fabric in creating efficient, scalable, and impactful data solutions. This project streamlines the process of monitoring, analyzing, and presenting transportation data, providing critical insights to stakeholders.
