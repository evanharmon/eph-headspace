# AWS S3 Gateway Stored Volumes
- entire Dataset is stored on-site and async backed up
- great for loss of internet connection
- can recover locally or on Amazon EC2
- up to 1TB size
- backuped as EBS snapshots

## Gateway Cached Volumes
- only most frequently accessed data is stored locally
- cost effective, bad if internet goes down
- up to 32TB size

## Gateway Virtual Tape Library (VTL)
- for Glacier, called Virtual Tape Shelf
- used for backup and uses popular apps like NetBackup, Backup Xec, Veam, etc
- replaces iron mtn, etc

## Storage Gateway Software
VM image available for VMware ESXi or Microsoft Hyper-V

# Pricing
Gateway: per gateway per month
Snapshot: per GB per month
Volume storage: per GB per month
Data transfer out: per GB per month
