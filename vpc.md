# VPC

VPC is a private cloud / cloud datacentre and is globally available.

## IP addressing and CIDR blocks

- IPv4 32bit
- IPv6 128bit

4 Octet notation., routing prefix. CIDR notation represent a block of addresses.

## VPC Network

- VPC Network
- VPN
- VPC Peering
- Shared VPC
- Routes
- VPC Flow logs
- Private Access
- BYOIP

Careful creating VPC and automatic and custom modes as it will populate all the regions with subnets. 

## Shared VPCs

Common resources from multiple projects to a common VPC network. There is a host project and a service project. Generally they need to be in the same Organization. Exception is during a migration.

It is defined in a host project, in auto or custom mode.
Two sharing options - 
- Share all the subnets including newly created ones.
- Alternatively define which subnets to share. New subnets will not be shared by default

Can specify the shared subnets that can be accessed and this complements the IAM access controls.

## VPC Network Peering

Advantages over External IPs or VPNs- it has lower latency and no exposure to public internet.
In addition, using external addressing incurs ingress.

- Allows for internal address connectivity between VPCs.
- Does not have to be in the same organisation.
- Useful when you have multiple administrative domains, e.g. SaaS customers.

- Works with Compute, GKE and App Engine Flexible.
- Peered networks are configured independently. 
- Up to 25 VPCs.
- Has the same latency and throughput as private network in same network.

## Cloud Router (BGP and non-Google networks) and Network peering

Paths between devices. Cloud Router uses BGP, advertising ranges of subnets. Can create custom routes, but Custom Dynamic routes will update the Cloud Router. Most efficient way of routing traffic. It is not a physical device, it is part of Andromeda, Google's SDN stack.

Dynamic Routing modes

- Regional - only advertise subnets in the same region.
- Global - all subnet routes in VPC.

## VPN and IPSEC

## Cloud Interconnect
  - Dedicated
  - Partner

## Firewalls

## Private Service Connect
  Secure connections between networks and services

## Cloud Armor

Protects against DOS/DDOS. It is made up of a WAF at Layer 7. ML driven adaptive protection. OWASP.

- L7 filtering.
- Policies, IP, IP Range, Request Headers.
- Needs a load balancer to function.
- Cloud Armor is at the edge of the network at the PoP.

*Only available for services behind an HTTP/S load balancer*

## Cloud NAT
   
Network Address Translation provides outbound access to the internet for non-external IP'd devices.
- Cloud NAT is not a single device (NAT Proxy).
- Cloud Router provides the control plane for Cloud NAT.
- Can scale the number of addresses. It does not reduce network bandwidth.
- Allows outbound connection and inbound connections in response (related).
- No unsolicited inbound.


## Private Service Connect

Private consumption of resources across VPC networks.
- Define IP addresses for Google APIs/Services/Services in your own VPC
- Private Service Connect Endpoint
Access Service provider in another VPC (e.g. your own API endpoints in another VPC)