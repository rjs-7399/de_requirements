The document contains details about Ravi, a data engineer. Here's the content in text format:

**Profile** 
- Ravi is a CSE graduate from the year 2020. 
- He holds a data engineering experience of 4 years. Currently. 
- He is a Senior Data Engineer and his technical experience includes:
  - Python, 
  - Teradata, 
  - Apache Airflow, 
  - Kafka, 
  - Azure Data Bricks, 
  - PySpark and SQL. 
- He is experienced in the healthcare domain.

**Data modelling** 
- He is experienced in designing and developing basic data models for medallion architecture. (done) 
- He is able to explain the choice of schema, difference in star and snowflake schema, facts and dimension table. (done) 
- He is exposed to Azure Blob Storage and Docker for containerisation.

**Unit testing** 
- He is able to explain the:
  - parameterization, 
  - mocking the database, 
  - measuring the code coverage, (done)
  - exceptions, 
  - failures and capturing logging output. 
  - Mock the dependencies, markers.

**PySpark**
- He is able to discuss the:
  - lazy evaluation, (done)
  - partitions (done)
  - skewed data, (done)
  - fault tolerance (done) 
  - accumulators and broadcast variables (done)
  - AQE for automated broadcasting, Broadcast join. (done)
  - cache and persist functionalities for recovery mechanisms (done) 
  - He is used to work on projects working on batch data. (done)

**Databricks** 
- He is able to explain:
  - setting up a pipeline using Delta Lake, (done)
  - workflows, data quality checks, (done)
  - cluster configurations, (done)
  - tuning techniques for clusters, 
  - monitoring and logging. (done)

**SQL** 
- His understanding is good in the:
  - key constraints, 
  - indexing, 
  - data redundancy, 
  - normalization
  - query optimization techniques. 
  - He tries to write a query for the given scenario using CTE.

Summary - Overall, Ravi is a nice person and good at communication. His exposure in modelling, testing, PySpark, Databricks and SQL will match the requirements. He will be a good fit for the role. Select.



## I need to prepare these things mainly in detail:

- Pyspark:
  - lazy evaluation
  - partitions
  - skewed data
  - fault tolerance
  - accumulators and broadcast variables
  - AQE for automated broadcasting
  - Dataframe cache and persist for recovery mechanism.

- Databricks:
  - setting up a pipeline using Delta Lake, 
  - workflows, data quality checks, 
  - cluster configurations, 
  - tuning techniques for clusters, 
  - monitoring and logging.

- Unit Testing:
  - parameterization, 
  - mocking the database, 
  - measuring the code coverage, 
  - exceptions, 
  - failures and capturing logging output. 
  - Mock the dependencies, markers.


- Some best docs:
  - https://www.databricks.com/discover/pages/optimize-data-workloads-guide

- To understand AQE in pyspark:
  - https://youtu.be/bRjVa7MgsBM?si=vbDQyq23U78soHlD

## My Explaination on These questions:

### Pyspark

#### Data Skewness

- sometimes data we get might not be evenly distributed over the dataset.
- Let's understand with an example.
- Here we have two datasets customers and orders.
- customers table is having these columns:
  - customer_id
  - customer_name
  - region_id
  - signup_date
- orders table is having these columns:
  - order_id
  - customer_id
  - order_date
  - amount
  - region_id
- Now I want to perform join between customers and orders table where the key = region_id.
- Now let's see the distribution of region_id key in both the tables.
- Customer table
+---------+-----+
|region_id|count|
+---------+-----+
|        1|  156|
|        2|   30|
|        3|    6|
|        4|    8|
+---------+-----+
- Order table
+---------+-----+
|region_id|count|
+---------+-----+
|        1|  627|
|        2|   91|
|        3|   38|
|        4|   44|
+---------+-----+
