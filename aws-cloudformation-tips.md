# AWS CLOUDFORMATION TIPS

## Availability Zones
using parameter in templates - # of AZs differs per region

## Mappings
- only using Mapping in substacks.
- mappings are not as useful in Nested stacks. They have to be broken down to
individual parameters

## Roles / Instance Profiles
- keep Instance Profiles inside instance template since they are so tightly
coupled
- role kept out of instance template so adding/removing policies does not
trigger instance template re-build

## Parent Stack Gotchas
Non-parent create stack actions can prevent parent stack deletion if resources
from that parent stack are referenced

## Sub Stacks
Either need to use DependsOn or explicit Parameters when using General export
ref styles like  `Fn::ImportValue: !Sub "${ServiceName}SG"`

## Make own instance IP available in init file
(There are better ways to do this - but it gives an example of cfn-init work)
or create a networkinterface in cloudformation, add to instance as eth1, and sub ref it
Use caps string in metadata init file
```
            "/tmp/init-cluster.sh":
              content: |
                # Run from UserData in cloudformation
                # Cluster already initialized?
                sleep 10
                echo "Init Cluster"
                /opt/couchbase/bin/couchbase-cli cluster-init \
                  -c REPLACE_WITH_INSTANCE_IP:8091 \
                  -u Administrator -p password \
                  --cluster-username=Administrator \
                  --cluster-password=password \
                  --cluster-port=8091 \
                  --services=data,index,query \
                  --cluster-ramsize=256 \
                  --cluster-index-ramsize=256 \
                  --index-storage-setting=memopt
              mode: "000700"
              owner: "root"
              group: "root"
## UserData regex replace
          INSTANCE_IP=`(curl http://169.254.169.254/latest/meta-data/local-ipv4)`
          sed -i 's/REPLACE_WITH_INSTANCE_IP/'$INSTANCE_IP'/g' /tmp/init-cluster.sh
          ./tmp/init-cluster.sh
  ```

## Custom Resources - Always set a Timeout
When working with custom resources, if the lambda function crashes, you're
stuck for between 1 and 2 hours, because CloudFormation waits for a reply from
the (crashed) function for an hour before giving up. Therefore it might be good
to specify a short timeout for the stack while developing your lambda function
