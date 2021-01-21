# AWS ELASTIC BLOCK STORAGE

## Summary

Notes on using elastic block storage

## Resources

- [Fast Snapshot Restore](https://aws.amazon.com/blogs/aws/new-amazon-ebs-fast-snapshot-restore-fsr/)
- [Initialize](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-initialize.html)
- [Volume Monitoring](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-volume-status.html)
- [Calculate IOPs used](https://onica.com/blog/managed-services/calculate-aws-ebs-volume-iops/)

## Summary

SSD, General Purpose - GP2 (Up to 10,000 IOPS)
SSD, Provisioned IOPS - IO1 (More than 10,000 IOPS)
HDD, Throughput Optimized - ST1 - frequently accessed workloads
HDD, Cold - SC1 - less frequently accessed data
HDD, Magnetic - Standard - cheap, infrequently accessed storage

## Block Storage - Disk in the Cloud

Attached to an EC2 Instance

## Zones / Regions

Exist in specific AZ Zones NOT across multiple zones
stored in multiple physical locations at no addt'l charge

## EBS Databases

EBS complex transactional databases should be backed up using the database
management system so distributed transactions/logs can be checkpointed

## Backups

AWS does not perform any backups - customer must do this

## GP2 (General Purpose SSD)

99.999% availability
3 IOPS per GB up to 10,000 IOPS
Burst to 3000 IOPS for volumes under 1Gib

## Provisioned IOPS SSD (IO1)

designed for I/O intensive apps like relational DBs and NoSQL databases
Use if you need more than 10,000 IOPS

## Magnetic (Standard)

Lowest cost per gig of all EBS
for data accessed infrequently, like fileservers

## Limitations

- 1 EBS = 1 EC2, cannot share across multiple EC2
- 1GB to 16TB
- st1, sc1 cannot be root volumes

## Init State

raw, unformatted block devices
you can create file system on top of EBS volume

## Sharing EBS snapshots

Can be shared publically on a read-only permission level
can only share unencrypted

## Snapshots

- incremental, only blocks that have changed since last snapshot
- cannot share encrypted snapshots
- block-level, stored on S3, incremental
- first one can take a while, subsequent snapshots will likely be quicker
- may contain deleted files with sensitive data
- copy to new EBS volume to be sure deleted files are not included
- encrypted volumes are automatically encrypted snapshots, restores from

## Root Volume Snapshots

Taking a snapshot automatically stops the volume - beware on production!

## Wipe

DoD 5220.22-M or NIST 800-88 wipe methods available

## Encryption

- Encrypts on server that hosts EC2 instance, so data encrypted in transit from
  EC2 instance to EBS storage
- Only available on M,C,R,G EC2 instance types

## Best Practices

- encrypt EBS volumes and snapshots with AES-256
- take snapshots regularly since EBS limited to specific zones
- EBS volumes that serve as root, you should stop the instance before taking the
  snapshot. (Make sure EC2 won't terminate on stop)

## Snapshot Of RAID Array

Problem: take a snapshot, excludes data held in cache by applications and OS. Across multiple volumes in RAID array, this can be problematic due to interdependencies of the array

Solution: Stop application from writing to disk, flush all caches to the disk
Freeze file system
Unmount the RAID Array
Shutting down the associated EC2 instance

## Warning Status

volume is degraded or severely degraded

## Impaired Status

volume is stalled or not available
