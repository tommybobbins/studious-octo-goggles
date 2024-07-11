# Cloud Dataproc

Cloud dataproc is a managed large scale batch processing/ML service for Hadooop and/or Apache Spark.
It is commonly used for ETL/ELT. The servers can be ephemeral and PAYG.  Pre-emptible VMs can be used to bring down cost. Startup is very fast.

Nodes are configured Master/Workers and Jobs.
DataProc templates are used to automate this. 

It's recommended to use Cloud Storage Connection to prevent disks needing to be managed (performance trade-off). Open source Java library is used to connect to the Cloud Storage instead of HDFS. Connector is automatically installed.

## Benefits of Cloud Storage and Dataproc

- Direct Data Access.
- HDFS compatbility.
- InterOperable with Hadoop/Spark.
- In-place data manipulation.
- No overheads.
- Quick startup
