# Cloud Migrations

Where are you starting?

- On premise with legacy workloads.
- On premise with containerised workloads.
- In the cloud with legacy workloads.
- In the cloud with containerised workloads.

## Types of Migration

- Lift and Shift.
- Improve and Move. (Take some advantages of the cloud- Hadoop to cloud dataproc).
- Rip and Replace. Gut the systems and refactor. Challenging and costly.
- 


## Migrations Systems and Data

Use the Cloud Adoption Framework.

- Assess - scope and catlogue dependencies. Learn about GCP and build prototypes. TCO. Prioritize workload migrations.
- Plan -  Determine user and service identities, resource hierarchy. Groups and Roles. Network Topology. 
- Deploy - Configuration management tools. Container orchestration. Deployment automation. IaC.
- Optimize - Build and train team, monitor and automate everything. Codify everything. Use managed services. Reduce costs.

## Network Management Planning

Network migrations require planning. Software defined networking - Andromeda. Think about traditional networking versus service networking, working at a higher level of abstraction. We need to consider deploying workloads globally. 

On-premise connectivity needs to be considered. Regulatory requirements and compliance. Also think about Scalability, Latency and DR.

- VPC.
- Regions and Zones.
- Hybrid Connectivty options (VPN, Interconnect, etc).
- IP addressing (CIDR ranges).
- Service Networking.
- Domain Name Services.
 - Data transfer (time and cost for egress)

## Specialized Migration Sevices

- Database Migration Service, migrate and keep in sync
- Migrate for Anthos
- Migrate for Compute engine
- VMWare Engine
- BigQuery Transfer Service
- Transfer Appliance
- Storage Transfer Service (between clouds or datacentre to cloud)