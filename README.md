# Home Sales Analysis 

## Overview
This project analyzes home sales data using pysprak. We perform various SQL queries on the dataset to extract insights related to house prices, features, and more. The dataset is sourced from an AWS S3 bucket and processed using Spark SQL.

## Dependencies
To run this project, you'll need the following dependencies:
* Apache Spark 3.5.0
* findspark
* pyspark
* py4j


## Code Structure
* Environment Setup: Downloads and extracts Spark. Initializes findspark to locate Spark in the system.
* Data Loading: Reads the home sales data from an AWS S3 bucket into a Spark DataFrame.
* Data Exploration: Shows the first 20 rows of the DataFrame. Creates a temporary view of the DataFrame for running Spark SQL queries.
* SQL Queries:
  * Computes average prices based on various conditions:
   * Four-bedroom houses.
   * Three-bedroom, three-bathroom houses built each year.
   * Three-bedroom, three-bathroom houses with two floors and a minimum of 2000 sqft.
   * Homes with a price greater than or equal to $350,000, grouped by view rating.
* Performance Metrics: Measures the time taken to execute specific queries using Spark SQL.
* Data Partitioning: Partitions the DataFrame based on the 'date_built' field and saves it in the Parquet format.
* Parquet Data Analysis: Reads the partitioned Parquet data into a new DataFrame. Executes the same SQL query on the Parquet DataFrame and measures its execution time.
* Cleanup: Uncaches the temporary table to release memory resources.

## Usage
Execute the code cells sequentially in a Jupyter Notebook or any Spark-supported environment.

## Results
The project showcases various insights from the home sales data, such as average prices for different house configurations and the influence of view ratings on home prices.

## Conclusion
This project demonstrates the power of Apache Spark in analyzing large-scale datasets efficiently. The Spark SQL queries provide valuable insights into the factors affecting home prices, helping stakeholders make informed decisions.
