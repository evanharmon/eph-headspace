# AWS EC2 PLACEMENT GROUPS
used for low-latency, high throughput

## Availability Zones
A placement group CANNOT span multiple AZs

## Naming
must be unique across AWS account

## Instance Types
Compute Optimized, GPU, Memory Optimized, Storage Optimized

## Multiple Instances
AWS recommends homogenous instances within placement groups. Same size / family

## Merging
Placement groups CANNOT be merged

## Movement
Existing instance CANNOT be moved into a placement group, new instance has to be
launched in to the placement group
