# Cloud SQL

Relational Database

- Structured Data.
- Predefined schema.
- Transaction processing applications.
- Strong consistency.
- Predefined schema.
- Structures (Tables, Indexes, Views, Constraints, Partitions).
- ACID transactions.
- Strong Consistency.
- SQL (DML) , DDL (Create table, alter index etc).

Cloud SQL Types - Regional data store, can use multiple zones, multi-region *for backups* only.

- MySQL
- Postgres
- SQL Server

Use when the storage requirements is < 30TB, otherwise Cloud Spanner.

## Normalization

- Rules for structuring data in tables.
- Unique ID for each row.
- Only attributes associateed with the key.
- Balancing act - performance versus data anomoly risk.

## Cloud SQL Auth Proxy

- Public IP
- Private IP
- Applications connect through SQL Auth proxy.

Validates credentials, Public and Private endpoints, Secures connection. Can run proxy client remotely.
Client app <-> Proxy Client <-> Proxy server <-> Instance
Setup using 
- Cloud SQL Instance to connect to
- Port to listen to
- Credentials
- Service account is recommended, create credentials file specific to the instance, explicitly linked in the cloud sql auth proxy and can be duplicated in the system image.

Create a database within the CloudSQL frontend.
