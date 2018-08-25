# AWS SYSOPS

## AMIs
Prebake for speed to recovery

## DynamoDB
Use to speed up recovery. Good in preparation phase to copy data to another
region / s3

## EBS / Cloudwatch
General purpose limited to 10k IOPS
Monitor for exceeding 3k.
Increase instance GB size to get more IOPS

Monitor for hitting 10k, switch from general purpose to provisioned at 10k

## EBS / Cloudwatch / Metrics
VolumeQueueLength is read / write operations waiting to be completed. If going
up then you are hitting IOPS limit

# EBS Pre-Warming
Only need to do this after restoring from snapshot.
Initializing every storage block
