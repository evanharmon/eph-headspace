# AWS EC2 RAID
RAID 0 or RAID 10 most common on AWS

## Striping
dividing body of data into blocks and spreading data across multiple devices

## RAID 0
Striped, No Redundancy, Good Performance

## RAID 1
Mirroed, Redundancy

## RAID 5
3 disks or more
Good for reads, bad for writes
AWS DOES NOT RECOMMEND EVER USING RAID 5'S

## RAID 10
Striped & Mirrored, Good Redundancy, Good Performance

## Raid Snapshot Problem
Snapshots exclude data held in cache by apps and/or the OS. Doesn't matter on
single volume but does in a RAID array bc of interdependencies

## Raid Snapshot Solutions
Freeze the file system
Unmount the RAID Array
or
Shut down associated EC2 instance - EASIEST
