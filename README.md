# End-to-End Apache Spark Data Pipeline: Apple Analysis

## Overview
This project follows a hands-on tutorial from The Big Data Show on YouTube. The focus of this project is on creating multiple ETL (Extract, Transform, Load) pipelines using PySpark, DataBricks, and different data sources such as CSV, Parquet, and Delta Tables. It demonstrates the use of design patterns like the Factory Pattern to streamline handling multiple data sources.

You can check out the full tutorial on The Big Data Show [here](https://youtu.be/BlWS4foN9cY?si=pVfp5rw-uZYrP4Vi).

## Tools and Concepts
- PySpark DataFrame API: For data transformations and manipulations.
- Spark SQL: For complex queries and business logic.
- Delta Tables: For efficient and reliable data storage.
- Factory Pattern: To handle multiple data sources dynamically.
- DataBricks: For pipeline orchestration and execution in a cloud environment.

## Data Pipelines
The project implements two distinct data pipelines:

### 1. Identifying Customers Who Bought AirPods After Buying an iPhone
- Data Sources:
    - Transaction Data: CSV files
    - Customer Data: Delta Table
- Logic: Used the LEAD() window function to identify the next product purchased by a customer after buying an iPhone.
- Optimization: Implemented Broadcast Join for efficient joining of large datasets.

### 2. Identifying Customers Who Only Bought AirPods and an iPhone
- Data Sources:
    - Transaction Data: CSV files
    - Customer Data: Delta Table
- Logic: Applied the COLLECT_LIST() function to group all products purchased by each customer.
Filtered customers to include only those who purchased AirPods and iPhones exclusively.
- Optimization: 
    - Used Broadcast Join for efficient data merging.
    - Partitioned the results by location to improve query performance and data organization.

## Conclusion
This project marks my first attempt at building an end-to-end data pipeline using DataBricks and PySpark. It has been an incredible learning experience, and I owe a big thanks to the creator of The Big Data Show for providing such an informative and hands-on tutorial. This journey has not only deepened my understanding of PySpark but also given me confidence in tackling real-world data engineering challenges.
