Ride Cancellation Analytics using Databricks Lakehouse
Project Overview

This project builds a Databricks Lakehouse solution to analyze ride bookings and cancellations for ride-sharing platforms. The goal is to identify cancellation patterns, revenue leakage, and operational inefficiencies by implementing a Medallion Architecture (Bronze, Silver, Gold layers) using Delta Lake.

Architecture: Medallion Framework
Bronze Layer (Raw Data Ingestion)
Ingested raw CSV datasets (rides + master tables) into Delta tables.
Data stored in its original format with minimal transformations.
Handles schema evolution and supports incremental file ingestion.

Key Operations:

Load CSV files into Delta tables
Store raw ride booking data
Maintain historical data for traceability
Silver Layer (Data Cleaning & Transformation)
Cleaned and standardized raw data to create a reliable dataset.
Applied business logic and handled data quality issues.

Key Operations:

Removed nulls and duplicates (Booking_ID as primary key)
Standardized column formats (Date, Time → Timestamp)
Cleaned cancellation fields and inconsistent values
Joined ride data with supporting datasets (if applicable)
Performed MERGE (UPSERT) for incremental data loads
Applied Delta operations:
UPDATE → Correct incorrect values
DELETE → Remove invalid/test records
Time Travel → Track historical changes

Outcome:

Clean, consistent, and validated dataset ready for analytics
Gold Layer (Business Aggregations & Insights)
Built aggregated tables for reporting and dashboards.
Focused on business KPIs and decision-making metrics.

Key Outputs:

Cancellation rate by city and vehicle type
Driver reliability and cancellation frequency
Peak hour ride demand and cancellation trends
Revenue leakage due to cancellations
Customer behavior (repeat cancellations)
City-wise demand distribution
Wait time and delay analysis
Executive KPI summary (total rides, cancellation %, revenue lost)
Incremental Processing
Simulated daily ride data ingestion
Used Delta Lake MERGE operation to:
Insert new records
Update existing records
Ensured efficient and scalable data updates
Technologies Used
Databricks
PySpark
Delta Lake
SQL
Key Insights
Identified high cancellation zones and peak failure hours
Measured revenue loss due to cancellations
Detected customer cancellation patterns
Analyzed driver performance using ratings and trends
Improved understanding of ride demand across locations
