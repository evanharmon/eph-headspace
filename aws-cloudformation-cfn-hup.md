# AWS CLOUDFORMATION CFN-HUP

## Sample cfn-hup autoloader files
Adjust path and action for actual ec2/launch config instance name
If using configsets like install_all, edit action
```
 /etc/cfn/cfn-hup.conf:
              content: !Sub |
                [main]
                stack=${AWS::StackId}
                region=${AWS::Region}
              mode: 000400
              owner: root
              group: root
            /etc/cfn/hooks.d/cfn-auto-reloader.conf:
              content: !Sub |
                [cfn-auto-reloader-hook]
                triggers=post.update
                path=Resources.LaunchConfig.Metadata.AWS::CloudFormation::Init
                action=/opt/aws/bin/cfn-init -v --stack ${AWS::StackName} --resource WebServerInstance --configsets InstallAndRun --region ${AWS::Region}
              mode: 000400
              owner: root
              group: root
```

## Sample cfn-hup autoloader services startup
```
services:
            sysvinit:
              cfn-hup:
                enabled: true
                ensureRunning: true
                files:
                  - "/etc/cfn/cfn-hup.conf"
                  - "/etc/cfn/cfn-auto-reloader.conf"
```
