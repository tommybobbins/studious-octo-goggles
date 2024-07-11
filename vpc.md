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

## VPC Peering

## Shared VPCs

Common resources from multiple projects to a common VPC network. There is a host project and a service project. Generally they need to be in the same Organization. Exception is during a migration.

It is defined in a host project, in auto or custom mode.
Two sharing options - 
- Share all the subnets including newly created ones.
- Alternatively define which subnets to share. New subnets will not be shared by default

Can specify the shared subnets that can be accessed and this complements the IAM access controls.

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

Protects against DOS/DDOS

## Cloud NAT
   