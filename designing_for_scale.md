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

# Operational Considerations

# Security and Compliance

# Reliability Engineering
