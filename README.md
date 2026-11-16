# World Bank Medallion Data Pipeline

Academic project combining data engineering and data analytics using
Python, PySpark, Spark SQL and Hadoop HDFS.

The pipeline collects data from the World Bank Indicators API,
organizes it into Bronze, Silver and Gold layers, and produces
SQL analyses and visualizations.

## Project Objective

Build a batch data pipeline covering the main stages of working
with external data: ingestion, storage, cleaning, transformation
and analytical exploration.

## Dataset

The project uses 8 economic and demographic indicators covering
2010–2024, including GDP, GDP growth, GDP per capita, inflation,
government debt, revenue, government consumption and population.

The source contains both countries and international aggregates.

Data source: World Bank Indicators API.

## Technologies

- Python
- PySpark and Apache Spark
- Spark SQL
- Hadoop HDFS and WebHDFS
- JSON and Parquet
- pandas and Matplotlib
- requests

## Pipeline Architecture

### Bronze — Raw Data

- Extract indicator data through the World Bank API.
- Preserve the original records and extraction metadata.
- Store the raw data as JSON in HDFS.

### Silver — Cleaned Data

- Expand nested JSON into a tabular structure.
- Convert columns to appropriate data types.
- Normalize empty fields and remove duplicate records.
- Save the transformed data as Parquet and upload it to HDFS.

### Gold — Analytical Data

- Add entity identifiers and classifications.
- Create missing-value flags and decade groupings.
- Store the enriched dataset as Parquet in HDFS.

### Analysis and Visualization

- Query the Gold dataset using Spark SQL.
- Apply CTEs, conditional aggregations and window functions.
- Profile missing values.
- Explore macroeconomic trends with pandas and Matplotlib.

## Repository Contents

- `worldbank_medallion_pipeline.ipynb`: project description,
  pipeline implementation, SQL queries and saved visualizations.

## Execution Requirements

The notebook requires a configured Spark and Hadoop environment
with access to HDFS through WebHDFS.

Before execution:

1. Install the required Python libraries.
2. Adjust the Hadoop hostname, port, user and storage paths.
3. Ensure that the required HDFS directories exist and are writable.
4. Restart the notebook kernel and execute the cells in order.

The PySpark version must be compatible with the Spark environment.
Installing the Python libraries alone does not configure Hadoop.

## Current Status and Limitations

This repository contains the academic notebook and its saved outputs.

- Environment settings currently reference the academic cluster.
- The Gold analysis should select a single extraction to avoid
  mixing repeated snapshots.
- Some exploratory fiscal indicators and chart interpretations
  require revision before reuse.
- Automated tests and a reproducible environment specification
  are planned improvements.

## Author

Miguel Ferreira

[LinkedIn](https://www.linkedin.com/in/miguel-ferreira-567678268/)
