# Cloud Spanner

Managed SQL databases. Globally scalable.

- ACID
- Globally distributed.
- SQL
- Managed - automatic replication, no downtime.
- Built on postgres

## When to use

- Structured data
- Predefined schema
- ACID transactions
- Cloud SQL insufficient (too much data, more scalability required)

## PITR

- Retain all versions of data and schema from 1hr to 7 days.
- Recover a portion of the database to perform a stale read specified query at that timestamp.
- Recover an entire database and specify a timestamp.

## Limitations

- 100 databases per instances
- 2TB of data per node
- 5000 tables per db
- 1024 columns per database
- 10MB max data per column
- 32 Indexes per table
- 10,000 indexes per database.

## Creating

- Regional or multi-region
- Regional 3 read-write replicas in 3 separate zones. $0.9 / hr.
- Multi-regional - within US, Asia, EU - $9 / hr.
- 3 nodes = 3 * 2 TB = 6 TB.