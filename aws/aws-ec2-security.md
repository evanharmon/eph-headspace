# AWS EC2 SECURITY

## Levels of Security
- OS
- firewall
- signed API calls

## Hypervisor
- AWS has highly customized the Xen hypervisor
- guest OS has no elevated access to CPU

## CPU privilege modes/rings
- ring 0 is most privileged and is typical OS privilege
- guest OS on AWS runs at Ring 1
- AWS runs applications on least priveleged Ring 3

## AWS Firewall
- resides within Hypervisor layer between physical network interface and the
instance's virtual interface
- all packets must pass through this layer

## RAM
- physical RAM is separated from instance similar to the firewall mechanism
- scrubbed (set to zero) by hypervisor when unallocated before re-allocated

## Disk Access
- customer instances have no access to raw disk devices - only virtualized disks
- every block of storage is auto-reset to prevent customer's data being exposed
to another customer

## Use IAM Roles For New / Auto-Scaled Instances
- temporary credentials created by AWS and shared with instance via EC2 Metadata
Service
- temporary security credentials available prior to expiration of current active
credentials - helps with transition

## EC2 Instance Logging Network Access
- to catch unwanted access attempts - make use of an OS level logging tool like
iptables and log events to CloudWatch/S3

## Best Practice
Run encrypted file system on top of virtualized disk device
