# EHR Healthcare

- Cloud SQL (<30TB) or Cloud Spanner (Regional).
- Rapidly scale storage
- EKS, MIGs, Unmanaged instance groups if Legacy
- Multi-Region resources.
- Version control, git, pipelines. Cloud Build. Cloud Container Registry.
- Memorystore for Redis.
- MongoDB -> Firestore/Compute Engine
- Microsoft AD with IAM.
- Observability - Cloud Monitoring / Cloud Logging
- Insights into healthcare trends - BigQuery  + AutoML.
- Reduce latency. Geographic location.
- Regulatory compliance - encryption at rest, TLS.
- CMK ? Customer Supplied keys ?
- Data Loss Prevention.
- Audit logs to Cloud Storage bucket.
- Decrease infrastructure admin costs so Managed services.
- Upload data (Cloud Function->Cloud PubSub->Cloud Storage)
- IaC.

# HRL

- TPU in Compute Engine - tensorflow. MIG. Networks wider. Additional data. 
- ML capabilities
- Expose predictive models - API endpoints, IAP. 
- Streaming data, 
- Fan engagement data / Season long data - BigQuery.
- Cloud PubSub as more data.
- Cloud DataFlow for perforning the stream processing and run the ML as part of the dataflow.
- Reduce latency - CDN.
- Network interconnects, direct interconnects, partner interconnects.


# Mountkirk Games

- Cloud Spanner globally managed transactions.
- Log Router to route logs to cloud storage or BigQuery.
- GPUs in GKE.
- Autoscaling.
- Managed resources whenever possible.
- Cloud BigQuery for ML

# TerramEarth

- ML capability
- Autoscaling
- GKE 
- IaC
- CICD
- IAM for remote developers, attribute based authentication
- IAP
- Exports from BigQuery to provide back to dealers in APIs - Cloud DataFlow.
- Customer API services (GKE)
- Secret Management
- IAM Least privilege.