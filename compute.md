# Compute 

GPUs are not available in all regions, 
- A2 NVIDIA A100 GPU
- N1 Intel Skylake

- Reservations are reserved instances.
- Preemptible VMs are equivalent to Spot instances in the AWS world.
- It is possible to block SSH keys project wide.
- Instance templates are the equivalent of an AMI.
- Instance Groups are ASGs, Autoscaling, Autohealing, Load balancing.

### Instance template

Description of a Virtual Machine, Machine Type, Confidential Computing, Security, Container, Operating System, Boot disk, Networking, Tenancy.

### Stateless Managed instance Group

Collection of Virtual machines managed as a unit, autoscaling, autohealing, load balancing, autoupdating. Created from an Instance template. Stateless managed instance groups consist of ephemeral disks + managed data. Commonly used for Web backends or batch processing. Multi-zonal is possible. Predictive autoscaling option. Cool down period, scale in controls. Health check (e.g. TCP, 80, check interval, timeout, thresholds)

### Stateful Managed instance group

Stateful policy, the disks are stateful, *no autoscaling*, autohealing, load balancing, autoupdating. The configuration is per instance.  Commonly used for databases, legacy apps. Template Instance + Stateful Policy (how disks are configured) + Per-instance config = Instance. Predictive autoscaling option. Cool down period, scale in controls. Health check (e.g TCP,80, check intervals, timeout, thresholds)

#### Stateful Configuration

Disks are listed for making instances stateful, on permanent instance deletion, detach or delete the disk.

### Unmanaged instance group

Heterogeneous (can be different configurations),  has no instance template, no autoscaling, no rolling update support and is generally associated with legacy clusters. Does support load balancing.

### Confidential VM Overview and Security Features

Memory encrypted with keys which reside in dedicated hardware, not available to the hypervisor.
Attestation - verify the state of the VM to ensure key componenents haven't been tampered with.
Known as _Trusted Execution Environment_
Can also use Shielded VMs - Secure Boot [], TPM (Measured Boot) [], Integrity monitoring.

### Ops Agent on VM Instances

Installs fluent-bit and opentelemetry configured to push logs and metrics respectively.

### Disk hierarchy

|Boot Disk|Features|IOPS (R/W)|Non-boot disk availability|
|---|---|
|Standard|Lowest cost| 375/750| Regional & Zonal |
|Balanced|Higher cost| 3000/3000 | Regional & Zonal |
|SSD | SSD, higher cost, best price per IOPS|15000/9000| Regional & Zonal |
|Extreme | NVME | >=500GB, highest write throughput| 60K IOPS| Zonal Only (120K IOPS) |

### TPUs

VMs can be created which contain TPUs, (associated with Tensorflow). Lower precision floating point operations compared to GPU. Deep learning does not necessarily require high precision of a GPU. TPU version software is a dropdown option when building a Cloud TPU. Pre-emptibility is a must, which means that the cost can be reduced by a factore of 4 (but can be reclaimed by Google at any time).


## Encryption at rest

- Encoding data that cannot be converted back to the original form.
- Keys are used with encryption algorithms to create encrypted data
- AES256 used on all hardware
- Data is grouped into chunks and AES256 encryption
- Data chunks are encrypted with it's own data encryption key.
- Data encryption key is encrypted with a key encryption key (CMK or GMK). This prevents data blocks from being needed to be re-encrypted when the CMK or GMK key is rotated.

## Encryption in transit

All data is authenticated but not encrypted inside the VPC. ALTS is used.
On public internet all traffic is encrypted.