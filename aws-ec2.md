# AWS EC2

## Check Metadata While SSH'd In To Instance
NO SUCH THING as user-data for an instance as a curl
`$ curl http://169.254.169.254/latest/meta-data`

## Get Private IP Of EC2 Instance
`$ curl http://169.254.169.254/latest/meta-data/local-ipv4`

## View Script Of Userdata On Instance
`$ cat /var/lib/cloud/instance/scripts/part-001`
`$ cat /var/lib/cloud/instances/$INSTANCE_ID/user-data.txt`

## cloud-init Log File
`$ cat /var/log/cloud-init.log`

## Termination / Delete
- termination protection is turned off by default
- EBS-backed instance, default action is for root EBS volume to be deleted
when instance is terminated

## Reserved Instances
Can be transferred between AZs
CANNOT be transferred between Regions

## Admin Access
you have admin access to the underlying resources / os

# Encryption
use third party tool (bit locker, etc) to encrypt root volume
- root volumes cannot be encrypted by default
- cant encrypt device where OS is installed

## Dedicated Hosts
Used for .GOV
