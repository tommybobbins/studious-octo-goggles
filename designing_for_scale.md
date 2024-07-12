# System Design Considerations

## Geographic Regions and Zones.

- Use regions in close proximity to users. 
- Use regions to satisfy geographic requirements.
- Use Cloud interconnect for high speed access to the cloud.
- Use Global Load balancers to provide single IP.


## IAM

- Use Google account, Service Accounts, Google Group, Workspace domain, Identity Domain.
- Use IAM Least privilege.
- Use Service Accounts with limited access to one service.
- Use resource hierachy.


## Compute 

Do not use Public IPs.
Do not use IP Forwarding.


## Networking

- Use separate VPC for each OU.
- Use common VPC for shared services.
- Isolate sensitve applications and data to their own VPC.
- Use Private DNS.
- Audit Network Access.
- Limit RDP + SSH.

## Storage

- Identity storage requirements and use appropriate service.
- Store data close to applications that use it.
- Do not include sensitive information in the Bucket names.
- Use CDN.
- Consider compliant and regulation when choosing storage locations.

## Databases

- Understand consistency requirements.
- Choose keys to avoid hot spotting.
- Use connection pooling and exponential backoff.
- Use Cloud SQL Proxy to connect to database.
- Limit DB Privileges.

## Data Pipelines and Analysis

- Determine if pipelines require exactly once or at least onces delivery.
- Decouple using Cloud Pub/Sub and/or Cloud Storage.
- Use Partitioning and Clusterint in BigQuery.

# Operational Considerations

## Release Engineering

 - Enforce policies through automation.
 - Frequent releases.
 - Ensure consistency with build tools and versioning.
 - Automate testing (unit, integration and System).
 - CICD.

## Monitoring

 - Choose metrics based on business requirements.
 - Use Cloud Monitoring and Cloud Logging.
 - Deploy agents to collect custom metrics if required.
 - Use alerts.

## Disaster recovery

- Define SLA and SLO.
- Define RTO and RPO.
- Plan for application and data recovery.
- Test DR Plan repeatedly.

# Security and Compliance

- Authentication and Authorization (Least Priv, treat each application as a trust boundary, grant roles at smallest required scope, grant roles to groups, use IAM conditions, use VPC Service Controls)
- Auditing - use cloud audit logs and export them to cloud storage. Restrict access to the logs
- Compute - disable external IPs. Use Google curated images.
- Use Workload Identity
- Use GKE node auto-upgrade.
- Define service perimeters with VPC Service controls
- Encryption at rest enabled by default.
- Use service accounts.
- Use firewall rules.
- Use Google Managed keys for easy administration.
- Use object versioning for Cloud storage
- Limit deletion permissions.
- Delegate Administrative controls for buckets
- Limit access to database
- Do not make BigQuery publically available. 
- Use Secrets Manager
- Use Data Loss Prevention Service.

# Reliability Engineering

- Create redundancy.
- Use multi-region.
- Degrade services when overloaded.
- Prevent or mitigate traffic spikes (cloud pub/sub). Decoupling.
- Ensure changes can be rolled back.
- Promote and upgrade over extended period of time.
- Automate build, test and deploy.
- Test DR procedures.
- Use chaos engineering.
- Plan for incident response.

# Load Shedding and Client Throttling

Load shedding is dropping data that exceeds the system's capacity to deal with it.
Upstream Throttling is a client measuring the downstream response, then buffering requests so that they don't flood the backend.