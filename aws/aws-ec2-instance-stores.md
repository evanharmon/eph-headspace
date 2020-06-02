# AWS EC2 INSTANCE STORE

## EBS and Instance Store Volumes
- can be rebooted without losing your data
- default, ROOT volumes will be deleted on termination

## Instance Stores
- ephemeral Storage - less durability. If host fails, your instance store/data
is gone
- can only be added when instance is created
- instance cannot be stopped when an instance store is used
- created from a template stored on S3

## EBS
- created from an EBS Snapshot
- can be stopped without losing data
- can be attached to an Instance after it is launched
- can be set not to delete volume when instance is terminated/deleted
