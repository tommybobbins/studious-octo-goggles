# Big Query

Big Query is serverless associated with data warehousing. 

- Uses SQL.
- Petabyte scale.
- Not a relationship database, Analytical database.
- Built in ML (BigQuery ML), using SQL.
- BigQuery BI Engine (addon).
- BigQuery GIS.
- BigQuery Omni (Azure, AWS).


## Tables and Views

### Tables

- Tables support scalar and nested structures
- Stored in a columnar format
- Partitioning

### Views

- Projection of one of more tables
- Views can be materialized (can be exported out to a table)


### Datasets

- Collection of tables and views
- Associated with one project
- All tables and views are in a dataset.

## Query Data

- SQL GUI
- bq
- Storage API (Spark, Tensorflow, Dataflow, Pandas)

## Federated Data Access

- Bigtable
- Cloud SQL
- Cloud Storage (Parquet, ORC)
- Google Drive (CSV, JSON, Avro, Sheets)

## BigQuery Scalar datatypes

- Numeric
- Integer
- Float
- Time Scalars - Date, Datetime, Time, Timestamp
- Boolean
- String
- Bytes - variable length binary data
- Structs - container of ordered fields.

## Access Controls

Either:

- Org or Project level.
- Dataset level
- Table or view level.

Permissions are based on the resources: Tables, Datasets, Jobs, Models, Reservations, Saved Queries

- BigQueryAdmin - Manage everything
- BigQuery Data Owner/Editor/View - apply either at Dataset or Table/View level.
- BigQuery Resource Admin/Editor/Viewer - All BigQuery resources.
- BigQuery User - At Project or Table/View level. Allowed to Create new datasets within Project. This user will then become the Data Owner so be careful.

Column level security is based on tags, tags associated with IAM access.

### Basic Roles

- Projects Viewer/Editor/Owner
- Datasets Reader/Writer/Owner
- Not recommended 

## Partition Table

Tables can be divided into segments called partitions. This improves query performance and lowers cost.

- Partition by ingestion time - daily date based partition. Ingestion time determines partition. A pseudo column is created _PARTITIONTIME which is a date based timestamp. Can reference this in queries
- Partition based on date or timestamp column. Each partition holds one time unit of data.  _NULL_ is created in partition column when nulls in partition column. _UNPARTITIONED when values in column are outside the range.
- Integer range partitioning - use separate column with integery value. Specify, start and end of the range. Interval is one of those items in the range. Values which fall outside the range fall into the UNPARTITIONED partition.


