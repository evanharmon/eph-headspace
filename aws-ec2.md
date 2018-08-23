# AWS EC2

## Check Metadata While SSH'd In To Instance
`$ curl http://169.254.169.254/latest/meta-data`

## Get Private IP Of EC2 Instance
`$ curl http://169.254.169.254/latest/meta-data/local-ipv4`

## View Script Of Userdata On Instance
`$ cat /var/lib/cloud/instance/scripts/part-001`
`$ cat /var/lib/cloud/instances/$INSTANCE_ID/user-data.txt`

## cloud-init Log File
`$ cat /var/log/cloud-init.log`

## SPOT Instances
Most commercially feasible
Terminating Instances manually you are charged partial hour
AWS terminates then you are not charged partial hour

## Termination / Delete
- Termination protection is turned off by default
- EBS-backed instance, default action is for rooot EBS volume to be deleted
when instance is terminated

## Reserved Instances
Can be transferred between AZs
CANNOT be transferred between Regions

## Admin Access
you have admin access to the underlying resources / os

## Encrypted
Root volume NOT encrypted by default, have to use third-party tools
CANT encrypt device where OS is installed
