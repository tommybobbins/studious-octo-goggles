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

A Service Mesh controls how parts of an application communicate and share data. It's a dedicated infrastructure layer. Requests to servcies are routed through sidecars. Proxies implement policies to support a service (e.g security or logging)

Microservices do not need to implement these features, just deploy the Anthos service mesh.
It is based on Istio, provides for traffic management, observability and security.

## Cloud Run - Managed service

Is the future of App Engine.

Managed compute platform which allows containers to be run via requests or events. Cloud Run is serverless. Cloud Run automatically scales your container out to handle the received requests, then scales in when demand decreases. You only pay for the CPU, Memory and Networking consumed during request handling.

- Pay per use
- Up to 1000 container instances by default.
- Can use with IAP.
- Manage identities that can acces service or allow unauth access
- Containers isolated to gVisor sandbox.
- Service is the main abstraction. It is located in a region and can be across zones.
- Revision is a deployment of a service, it consists of a specific image and configuration.
- Container instances run revisions and autoscale based on load. 
- Concurrency, up to 80 (default) simultaneous requests (1-1000 min-max). Cloud Functions can only have concurrency of 1.
- 