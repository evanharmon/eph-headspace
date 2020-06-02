# AWS CLOUDFORMATION CFN-INIT

## Order
The cfn-init helper script processes these configuration sections in the
following order:
packages
groups
users
sources
files
commands
services

If you require a different order, separate your sections into different config
keys, and then use a configset that specifies the order in which the config
keys should be processed
```
UserData:
  Fn::Base64:
    !Sub |
      #!/bin/bash -xe
      yum update -y
      /opt/aws/bin/cfn-init -v -s ${AWS::StackName} -r PublicInstance --region ${AWS::Region}
```

## Install cfn-init Scripts In CentOS7
```
cd /opt
curl -O https://s3.amazonaws.com/cloudformation-examples/aws-cfn-bootstrap-latest.tar.gz
tar -xvpf aws-cfn-bootstrap-latest.tar.gz
cd aws-cfn-bootstrap-1.4/
python setup.py build
python setup.py install
ln -s /usr/init/redhat/cfn-hup /etc/init.d/cfn-hup
chmod 775 /usr/init/redhat/cfn-hup
cd /opt
mkdir aws
cd aws
mkdir bin
ln -s /usr/bin/cfn-hup /opt/aws/bin/cfn-hup
ln -s /usr/bin/cfn-init /opt/aws/bin/cfn-init
ln -s /usr/bin/cfn-signal /opt/aws/bin/cfn-signal
ln -s /usr/bin/cfn-elect-cmd-leader /opt/aws/bin/cfn-elect-cmd-leader
ln -s /usr/bin/cfn-get-metadata /opt/aws/bin/cfn-get-metadata
ln -s /usr/bin/cfn-send-cmd-event /opt/aws/bin/cfn-send-cmd-event
ln -s /usr/bin/cfn-send-cmd-result /opt/aws/bin/cfn-send-cmd-result
```

## Check CFN-INIT Script
```
cat /var/lib/cfn-init/data/metadata.json
```
