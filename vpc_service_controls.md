# VPC Service Controls

Create security perimeters around GPC services. They compleement IAM. Mitigates the risk of data exfiltration.


Used for sensitive data
 - Clients with privileged access don't have access to partner resources
 - Clients with access to sensitive data, only need to read.
 - It is independent of IAM, defence in depth.
 - Can prevent re-use of stolen credentials (allow access only from auth networks).
 - Data exfiltration by insiders or compromised cost.
 - Supports most GCloud services including Cloud Storage (non-VPC). 
 - Should be used as a go to for proecting sensitive data from Internal users.
 - Can extend perimeters to on-premise networks.

## How does it work? 

 - Clients within a perimeter that have private access to resources do not have access to resources outside the perimeter.
 - Data cannot be copied outside the perimeter (e.g. gsutil, bq).
 - Data exchange between clients and resources is determined using ingress and egress rules.
 - Context aware access to resources (service account or user)

