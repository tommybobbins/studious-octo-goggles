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
- Can set partitioning as a required filter at the table level. This requires a WHERE calues with the partition column.

Partition based on event_time is useful, require partition filter in the Partition and Cluster settings. Partition based on day.

## Date/Timestamp partitioning versus Sharding

Sharding can be used as follows:

- Use separate tables for each day.
- TABLE_NAME_PREFIX_YYMMDD
- Use Union in queries to scan multiple tables.

Partitioning is preferred over sharding because there is less metadata to maintain, less permission checks across the unions and better performance.

## Clustered tables

Use clustering when we need more granuality than partitioning provides. Commonly used filters or aggregations against the cluster columnns. If the cluster column has a high cardinality (many different values). When partition leads to less than 1GB per partition, use clustering.

- Data is sorted based on values in one or more columns.
- Can improve performance of aggregate queries.
- Can reduce scanning when cluster columns are used in the WHERE clause.

Clustering based on sensor_id, with the event_time partition, the clustering order of sensor_id makes most sense.

## Automatic Reclustering

- As new data is added to a table, data may be stored out of order
- BigQuery automically re-clusters in the background.
- For partitioned tables that use clustering, clustering is maintained within each partition.

## Creating a table

- Create dataset
- Create table, 

## Loading data

- Cloud Storage.
- Other Google services.
- Local machine.
- Streaming inserts.
- DML bulk load
- Cloud Dataflow -> BigQuery I/O Transform.

Loading methods - Big Query GUI, BigQuery API, bq command line.

### Performance considerations

Avro binary is preferred format

- Data Can be compressed or uncompressed.
- Compressed Avro files are not supported.
- Compressed Avro data blocks are supported.

Parquet has efficient encoding typically results in a better compression ratio and smaller files.
CSV and JSON files, BigQuery can load uncompressed files faster than compressed.

## BigQuery Transfer service

Move data into BigQuery from SaaS service. It is a managed, autoscaling service and can schedule loads. Access other data sources through connectors.

BigQuery Transfer Service Connectors have a marketplace in Google Cloud e.g. kafka connector. 

## BigQuery and IAM

Grant permissions to identities using roles. 

Identities (principals)
 - Users
 - Service Accounts
Roles are sets of permissions.
Permissions assigned to Identities via Roles.
Types of Role:
 - Predefined
 - Custom
 - Basic (legacy/Primitive roles). Not for Production.


### Grant Access

Grant access at multiple levels
 - Organization
 - Projects
 - Datasets
 - Tables and views
 - Rows and Columns

### BigQuery Permissions

Permissions apply to resources:

- Datasets
- Jobs
- ML Models
- Tables

Operations allowed:

- Get
- List
- Delete
- Create


## Column Level Security

- Control access to columns with sensitive data
- Create policies and check at query time whether a user has proper access.

### Steps to implement

- Define policy and taxonomy tags.
- Assign policy tags to BigQuery columns.
- Enforce access control on taxonomy.
- Edit column in console "Policy Tags (e.g. Business Criticality: High)"

## Row Level Security

Filter data in a table based on user conditions, complementing project, dataset, table and column level security.
Data can be hidden or displayed depending on user conditions.
Row level policy is applied to the table.
```` 
CREATE ROW ACCESS POLICY <name> ON <table> GRANT TO <group> FILTER USING (Region="US");
````

The following roles may still be able to access/infer the data with Row level security:

- Project Owner or Project creator ( Audit logs, create new projects)
- BigQuery Data Edit, Owner, Viewer (View error messages on queries)
- BigQuery Stackdriver metrics/Monitoring viewer roles (bytes processed and related data)
- Cloud Billing viewer permission (view BigQuery billing)

## BigQuery ML

Support for Machine Learning in SQL. Several kinds of models

- Linear Regression.
- Binary and Multiclass logistic regressions.
- K-means clustering.
- Time series forecast.
- Matrix factorization.
- Boosted tree and XGBoost
- Tensorflow (imported)
- AutoML tables (let the algorithm decide)

Why do this in BigQuery, labelled observations, training sets, test sets. ML, Prediction model. Accuracy stats.

### CREATE MODEL Options

- Model type
- Input Label columns
- Regularization
- Learning rate
- Early stop
- Standardize features
- Max Tree depth

Evaluate - apply test data.
Predict 

## BigQuery BI Engine

Fast in memory analysis service. Big Query data stored in memory up to 100GB/project/location and 10GB/table.
Optimises data movement between BI Engine in-memory storage.
Integrates with popular BI tools through SQL interface. (including data studio)
Uses Vectorized runtime inside the BigQuery API, metadata.
Low latency querying over small amounts of data. 