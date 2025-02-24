# Customer Information System

## Project Overview
This project implements a comprehensive **ETL pipeline** using **Informatica PowerCenter** to extract data from an **Oracle database**, transform it according to specific business rules, and load it into a **target data warehouse table**. The project focuses on optimizing data processing, ensuring high performance and data integrity.

## Project Workflow

### 1. Data Extraction
The ETL pipeline starts by connecting to an **Oracle database** to extract raw data. The extraction process is designed to handle large datasets efficiently, ensuring the system can process millions of records.

### 2. Data Transformation
The extracted data undergoes a series of **transformations** to meet the required format and business logic:
- **Sorting and Filtering**: Records are sorted based on predefined rules, and unnecessary or duplicate records are removed.
- **Data Enrichment**: The transformation phase involves enriching data through calculated fields, value mappings, and other data cleansing tasks to ensure consistency.
- **Parallel Processing**: To speed up the processing of large volumes of data, **parallel processing** techniques are used during transformation, enhancing overall performance.

### 3. Data Loading
After the transformation phase, the cleaned and formatted data is loaded into the **target data warehouse table**.
- Prior to loading, the table is **truncated** to ensure that the load is fresh and contains the most recent data.
- The data is loaded in **batches**, with each batch consisting of **10,000 rows**, allowing for efficient management of resources and reducing the risk of errors during data insertion.

### 4. Session Management and Error Handling
- **Session Logs**: The ETL process is monitored through detailed **logs** that track the progress of each stage—extraction, transformation, and loading. These logs provide insight into any errors or failures encountered.
- **Error Handling**: If any issues arise during the ETL process, detailed **error logs** are generated to help quickly resolve problems. The system includes mechanisms to prevent the interruption of data loading due to minor failures.

## Key Features
- **Optimized Data Processing**: Uses **parallel processing** to handle large datasets efficiently.
- **Error Tracking**: Comprehensive session logging and error management for smooth operation.
- **Batch Loading**: Loads data in batches to optimize database performance and resource utilization.
- **Data Integrity**: Ensures accurate and consistent data is loaded into the target table by using transformation rules and filtering.

## Technology Stack
- **ETL Tool**: Informatica PowerCenter 10.1.0
- **Database**: Oracle
- **SQL**: Used for querying and transforming data during the ETL process

## How to Run the ETL Pipeline

### 1. Configure Oracle Database Connection
Ensure that the connection to the Oracle database is correctly set up in Informatica PowerCenter.

### 2. Import the ETL Mapping
Import the mapping logic used for data extraction, transformation, and loading into Informatica PowerCenter.

### 3. Run the ETL Process
Execute the ETL process, and monitor the progress through session logs. The pipeline will truncate the target table and load fresh data.

### 4. Review Logs
After execution, check the session logs to ensure that the process completed successfully without errors.

## Future Enhancements
- Implement **incremental loading** to avoid truncating the target table and improve performance for large datasets.
- Optimize the **parallel processing** setup to handle even larger data volumes.
- Add more advanced **error handling** and **recovery** mechanisms to ensure smooth execution in production environments.
