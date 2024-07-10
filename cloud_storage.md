# Cloud Storage is object storage

## Suitable for Object storage.

- Images.
- Videos.
- Text.
- Archived data.
- Temporary storage (buffer) between services.
- Global access, internet accessible.

## Logical Organization

- Global namespace
- Buckets
- Folders
- Objects

## Storage Class

- Standard (frequent access, optimized for performance)
- Backup and Archival

| Storage Class | Notes | Use When | Retrieval/Modify | 
| --- | --- | --- | ---| 
| Standard | Frequent access, optimized performance | General | Anytime|
| Nearline | Reduced access| stored at least 30d | 30d | 
| Coldline | Reduced, reduced access | Stored at least 90d | 90d| 
| Archive  | Lowest access | Stored at least 1y | 1y |


You cannot ascend this table in Lifecycle Actions, only descend.

Regional storage, replicated across zones.
Dual-region - replicated across a pair of regions
Multi-region - Data duplicated across US/EU/Asia - auto failover.

## Object lifecyle management

Descend the lower cost tree, and retention policies.
Prevent deletion with Object holds.

## Security

- Encrypted (GMK, Customer Managed through Cloud Key Management service, Customer supplied).
- Bucket level access using Object ACL or IAM privileges
- Activity logs

## Loading data

### Small amounts

- Console
- Command line (gsutil)
- API

### Large amounts

- Cloud Storage transfer service - on-premise or between cloud storage buckets. One time or recurring transfer. (AWS-> GCP). Well suited to 100TB.
- Transfer appliance. Shipped to your datacentre, ship it back to Google. Google copy it to the bucket. Capatity is 40TB or 300TB.


## Signed URLs

- Time limited R/W access
- Generated URL
- Access withou  IAM
- Signed policy documetns, can control size/type/characteristics

## Lifecycle Policies

- Rules applied to buckets and contents
- Actions executed when condition applies

## Lifecycle Actions

- Delete - If versioned, creates non-current version.
- Delete - delete non-current version deletes object perm.
