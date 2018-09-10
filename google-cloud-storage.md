# GOOGLE CLOUD STORAGE

## Local SSD
375GB drives. Zonal resource

### Shutdown
local SSD drive data is LOST on instance shut down

### Charges
charged by the GB per month prorated

## Persisent Disk Service
similar to EBS. Replicated for durability

## Charges
pay per GB per month

### Data Transfer
data is still encrypted when in transit between the drive and the instance

### Performance
Slower than Local SSD. Max read is about 40k IOPS

### Resizing
Can resize up to 10TB but have to manually update VM just like AWS

### Snapshots
Incremental. Can use / delete full backups auto magically as if they were
complete

### Snapshots And Regions
Snapshots are available globally. Pay network transfer cost if between zones

### Snapshots Charges
pay per GB per month

### Mounting
PD drive can be mounted to multiple instances ONLY if they are all read-only
