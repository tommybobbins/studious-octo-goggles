# Anthos Computing Environment
 
Application Management Platform, heterogenous kubernetes platforms. Extends GKE for hybrid and multi-cloud. It provides services to create, scale and upgrade conformant Kubernetes clusters as well as a common orchestration layer.
Multiple clusters can be included in a Google Cloud Fleet for Common Management.

## Connectivity

- VPNs.
- Dedicated Interconnect.
- Partner Interconnect.


## Configuration Management

yaml files, declarative moduel. Store in git repository. Uses kubernetes resources like namespaces, labels and annotations.

## Why use Anthos

- Centralised management.
- Rollback.
- Single view of all cluster infrastructure.
- Instrumentation of code using Anthos Service Mesh.
- Centralised auditable workflows.
- Service protection with authorization and routing.



## Deployment

- Google Cloud (GKE, all the benefits, Cloud Run)
- On-premises VMware (L4 LB + Prometheus and Grafana)
- On premise bare metal
- AWS, Azure - EC2s, Azure VMs (AWS load balancers).
- Attached clusters - Only has Service Mesh, Config Mgt and Dashboards


## Multi Cluster Ingress

- Single consistent virtual IP address.
- Multi Regional, multi-cluster HA.
- Proximit based routing.
- Transparent cluster migration during upgrades and rebuilds.


Policies and Configurations for clusters which apply across clusters. Anthos Config management. Policy Controller.

## Anthos Service Mesh

## Anthos clusters, Ingress for Anthos

## Anthos clusters
-Google Cloud


