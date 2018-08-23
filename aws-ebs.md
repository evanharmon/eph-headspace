# AWS ELASTIC BLOCK STORAGE

## Block Storage - Disk in the Cloud
Attached to an EC2 Instance

## Zones/Regions
Exist in specific AZ Zones NOT across multiple zones
stored in multiple physical locations at no addt'l charge

## EBS databases
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
- can't mount multiple EC2 instances to a single EBS volume
- 1GB to 16TB

## Init State
raw, unformatted block devices
you can create file system on top of EBS volume

## Sharing EBS snapshots
Can be shared publically on a read-only permission level
can only share unencrypted

## Snapshots
- block-level, stored on S3, incremental
- first one can take a while, subsequent snapshots will likely be quicker
- may contain deleted files with sensitive data
- copy to new EBS volume to be sure deleted files are not included
- encrypted volumes are automatically encrypted snapshots, restores from
snapshots are also encrypted automatically

## Root Volume Snapshots
Taking a snapshot automatically stops the volume - beware on production!

## Wipe
DoD 5220.22-M or NIST 800-88 wipe methods available

## Best Practices
### Snapshots
Take snapshots regularly since EBS limited to specific zones

## Encryption
Encrypt EBS volumes and snapshots with AES-256

- Encrypts on server that hosts EC2 instance, so data encrypted in transit from
EC2 instance to EBS storage
- Only available on M,C,R,G EC2 instance types
