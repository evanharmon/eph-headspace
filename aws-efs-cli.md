# AWS EFS CLI

## Get Subnets For EFS File System Id
requires jq
```
$ aws efs describe-mount-targets \
    --file-system-id $FILE_SYSTEM_ID \
    | jq '.MountTargets[].SubnetId'
```
