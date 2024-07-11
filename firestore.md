# Cloud Firestore

Managed NoSQL Database, can be created regional or multi-regional.

Uses the document model
- Key value pairs
- Hierarchical

Two Modes

- Native mode
- Datastore mode

## When to use

- Semi-structured data
  - Schema is not fixed
  - May change over time
  - Different attributes across entities
- Query on multiple attributes
- Bounded ingestion volume - use BigTable is you are performing very high volume.


## Choosing a mode

- Datastore mode, server applications, no syncing with mobile.
- Native mode, mobile and web clients. Supports large number of connections.

## Entities

Describe a thing. An entity can be thought of as a row in a relational table.
A set of entities with similar attributes is equivalent to a table.
Entities have properties (compare to columns)
Related entities known as Kinds (compare to a table)

## GQL is used for querying

- An entity kind to which the query applies
- Filters based on the property values, keys and ancestors.
- Zero or more sort orders to sequence the results.

Once firestore is written to, the mode (Native=Mobile; Datastore=Server) cannot be changed.


## Indexes

- Indexes are *mandatory* for all queries because there are no scans.
- Can be single field or composite
- Some indexes are automatically created, atomic values, ascending and descending. Maps and arrays also get created too.

## Composite Index

- Index multiple fields
- Not automatically created, manual
- Used when querying and filtering using multiple attributes.

Any time you attempt a query not supported by an index, Firestore returns an error message with a link that you can follow to create the missing index.

## Limitations

- Queries with range filters on different fields are not supported.
- != operator *is supported*: https://cloud.google.com/firestore/docs/concepts/index-overview, https://cloud.google.com/firestore/docs/concepts/index-overview

## Transactions

Transactions are supported in Firestore.

- Serializable Isolation - Data being written cannot be read within the transaction.
- Can specify a read-only transaction which can be faster.
- Max duration of 270 seconds, 60 seconds idle. 
- Can modify 500 entities in a single transaction.
-  Resource limits, concurrency or internal error can lead to transactions failing.