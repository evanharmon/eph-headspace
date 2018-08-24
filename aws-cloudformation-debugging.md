# AWS CLOUDFORMATION DEBUGGING

## UserData Log
view logs `/var/log/cloud-init-output.log`

## Original UserData Script
`cat /var/lib/cloud/instance/scripts/part-001`

## Get Metadata
`/opt/aws/bin/cfn-get-metadata -s myStack -r myInstance  --region ap-northeast-1`

## cfn-init Logs
view logs `/var/log/cfn-init.log`, `/var/log/cfn-init-cmd.log`, `/var/log/cfn-wire.log`

## Re-run cfn-init
use your cfn-init line from your UserData
Good to debug troubleshoot cfn-hup cfn-init
```
$ /opt/aws/bin/cfn-init -v \
    -s ${AWS::StackName} \
    -r PublicInstance \
    -c MountConfig \
    --region ${AWS::Region}
```

## Re-run cloud-init
For only Initial modules
`/usr/bin/cloud-init -d init`
For all modules
`/usr/bin/cloud-init -d modules`

## Force instance to reboot and re-run cfn-init and cloud-init
```
 ( cd /var/lib/cloud/instance && sudo rm -Rf * )
 sudo reboot
```
