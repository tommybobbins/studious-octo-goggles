# Kubernetes

## Standard GKE Cluster

- Pay per resources (Nodes + Control Plane)
- User Configured Resources
- User Configured Autoscaling
- Regional or Zonal

## Autopilot

- Google Managed Control plane + Nodes.
- Pay per Pod (nodes sized based on Pod requests).
- Built in Security
- Regional only

## Public versus Private

VPC-Native cluster

Subnet ranges 
- Primary subnet range for node IPs (each node gets /24)
- Pod IP address range (each node can run 110 pods)
- Service IP address range 

### Public clusters

Control plane and nodes are accessible over the internet. Worker nodes can be protected using firewall rules.

### Private clusters

Better, cannot connect to nodes. Public and Private endpoint for the cluster endpoint. Must specify a /28. The 

- User VPC Network contains the nodes.
- Google Managed VPC Network - contains the control plane with a transparent VPC peering connection to the user VPC network with the nodes. If you are using a Private cluster, be careful of connecting to the controlplane via another VPC because of transiting rules.

