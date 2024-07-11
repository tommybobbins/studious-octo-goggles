# Cloud Dataproc

Cloud dataproc is a managed batch processing/ML service for Hadooop and/or Apache Spark.
It is commonly used for ETL/ELT. The servers are ephemeral and PAYG.  Pre-emptible VMs can be used to bring down cost?

Nodes are configured Master/Workers and Jobs.
DataProc templates are used to automate this. 

It's recommended to use Cloud Storage Connection to prevent disks needing to be managed (performance trade-off).

## Features

- Direct Data Access
- HDFS compatibilty
- InterOperable with Hadoop/Spark
- In-place data manipulation
- No overheads
