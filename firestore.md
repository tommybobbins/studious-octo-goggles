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