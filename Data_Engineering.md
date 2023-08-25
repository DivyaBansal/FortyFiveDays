# Data Engineering:

## DataLakes
Store all kinds of data (S3, HDFS etc.)
Loaded into warehouses via ETL.

## DataWarehouses
- Store high quality data
- Standard modeling techniques
-  Reliability through ACID transactions

## Lakehouses
Warehousing features on data lake storage 
- Support for both BI and ML/AI workloads
- Standard Storage Formatting
- Reliability through ACID transactions
- Scalability through underlying cloud storage


**ETL** - Data extracted can be transformed on the fly and eventually pushed to the Data Lake or Data Warehouse.  
**ELT** - Data is replicated to the Data Lake or Data Warehouse as is and Transformations performed inside of the System.

## Database Replication/Migration:

Source Database -> Target Database

If each transaction is replicated - it is possible to retain all ACID guarantees when performing replication.  

Realtime: If zero downtime replication and migration.

1. **Pull-Based:** A client queries the Source Database and pushes data into the Target Database  
    **Downside 1:** There is a need to augment all of the source tables to include indicators that a record has changed.  
    **Downside 2:** Usually - not real time, it might be performed hourly, daily etc.  
    **Downside 3:** Source Database suffers high load when migration is being performed.  
    **Downside 4:** It is extremely challenging to replicate Delete events.  

2. **Push-Based:** Triggers are set up in the Source Database. Whenever a change event happens in the Database - it is pushed to a target system.  
    **Downside 1:** This approach usually causes highest on-prem database load overhead.  
    **Upside 1:** Real Time
    
 