# studious-octo-goggles
Google Cloud Certified Professional Cloud Architect Study Notes


## Entity Types

|Entity|Notes|
|---|---|
|Organization|Root level structure, automatically created. Google Workspace Super Admins are granted the ability to create IAM roles.|
|Folders|Logically arrange Projects into Folders (Nested OU equivalent in AWS)|
|Projects|Projects can exist inside Folders or not|
|Resources|GCP Resouces exist inside a Project|

Billing accounts have a payment profile associated with them in a single currency. A Project and it's service level resources are linked to one Cloud Billing Account at a time. A single billing account can be responsible for multiple Projects.

## Compute 

GPUs are not available in all regions, 
- A2 NVIDIA A100 GPU
- N1 Intel Skylake

Reservations are reserved instances.
Preemptible VMs are equivalent to Spot instances in the AWS world.

### Confidentials VM Overview

Memory encrypted with keys which reside in dedicated hardware, not available to the hypervisor.
Attestation - verify the state of the VM to ensure key componenents haven't been tampered with.
Known as _Trusted Execution Environment_

### Ops Agent on VM Instances

Installs fluent-bit and opentelemetry configured to push logs and metrics respectively.

### Disk hierarchy

|Boot Disk|Features|IOPS (R/W)|Non-boot disk availability|
|---|---|
|Standard|Lowest cost| 375/750| Regional & Zonal |
|Balanced|Higher cost| 3000/3000 | Regional & Zonal |
|SSD | SSD, higher cost, best price per IOPS|15000/9000| Regional & Zonal |
|Extreme | NVME | >=500GB, highest write throughput| 60K IOPS| Zonal Only (120K IOPS) |