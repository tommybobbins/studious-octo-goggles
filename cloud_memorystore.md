# Cloud Memorystore

Highly available service. Can be divided into Redis and Memcached, choose the caching service .

Used for Database queries, Games and stream processing.

## Redis

Up to 300GB of storage.

Connect From:

- App Engine Flex/Standard.
- Compute Engine VMs.
- Cloud Functions.
- Cloud Run.
- GKE.

Features:

- Scale as needed, up to 300GB of storage, 12Gbps throughput.
- Redis protocol compliant.
- Basic tier (no replication, no cross zone, no automatic failover).
- Standard tier (replication, cross zone, automatic failover).


## Memcached

Distributed, in-memory kv store. Used for reference data, database query caching, session caching.
Instance == one cluster with the number of nodes, CPUs, Memory being configurable

- Maximum 20 nodes, all have to be same configuration
- 1 - 32 vCPUs
- 1GB to 256 GB per node.
- Maximum of 5TB per instance (cluster)

Memcached *does support Cloud Run* provided that Serverless VPC Access is enabled. https://cloud.google.com/memorystore/docs/memcached/memcached-overview

Connect From:

- App Engine Flex/Standard.
- Compute Engine VMs.
- Cloud Functions.
- Cloud Run.
- GKE.