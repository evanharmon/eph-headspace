# AWS EC2 EBS TERMINATION

## Scenarios and Results for EC2 Termination and EBS volumes
Check if EBS volume is set to Delete on Termination
```
$ aws ec2 describe-volumes \
    --volume-id vol-0e263d076e70e3ca8 \
    --query 'Volumes[*].Attachments'
```

## EBS DeleteOnTermination: True - Keep EBS Volume and VolumeID
These steps will require terminating / throwing away the instance
If set to True and you need the volume:
- set EC2 instance `Shutdown Behavior` to: `Stop` to protect from command-line
shutdown
- stop instance via the AWS Console
- detach the EBS volume via the AWS Console

## EBS DeleteOnTermination: True - Create New EBS Volume
If set to True and you can use a new volume id:
- create a snapshot of the volume in the AWS Console
- create new EBS volume from snapshot

## Configuration
* Shutdown Behavior: Terminate
* Protect Against Accidental Termination: False
* EBS Delete On Termination: True

### AWS Console Action: REBOOT
Root EBS volume data: *PERSISTS*
Addt'l EBS volume data: *PERSISTS*

### AWS Console Action: STOP
Root EBS volume data: *PERSISTS*
Addt'l EBS volume data: *PERSISTS*

### AWS Console Action: TERMINATE
Root EBS volume data: *DELETED*
Addt'l EBS volume data: *DELETED*

### Command-line Action: `reboot`
Root EBS volume data: *PERSISTS*
Addt'l EBS volume data: *PERSISTS*

### Command-line Action: `shutdown`
Root EBS volume data: *DELETED*
Addt'l EBS volume data: *DELETED*
