# GOOGLE CLOUD STORAGE
similar to AWS EBS
Replicated for durability

## Charges
per GB per month prorated
per operation
per GB network traffic egress

## Resources
offered as region or multi-region

## Data Transfer
data is still encrypted when in transit between the drive and the instance

## Performance
Slower than Local SSD. Max read is about 40k IOPS

## Resizing
Can resize up to 10TB but have to manually update VM just like AWS

## Snapshots
Incremental. Can use / delete full backups auto magically as if they were
complete

## Snapshots And Regions
Snapshots are available globally. Pay network transfer cost if between zones

## Snapshots Charges
pay per GB per month

## Mounting
PD drive can be mounted to multiple instances ONLY if they are all read-only
