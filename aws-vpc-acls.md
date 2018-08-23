# AWS VPC ACLS
Second layer of defense after security groups

## Features
- act on the subnet
- encompass all security groups under the subnet associated with them
- span multiple subnets

### Defaults On New ACLs
When you create a new ACL, All traffic inbound and unbound defaults to DENY
No subnet is assigned until you explicitly assign one to the ACL

### Can Override A Security Group Rule
Ex. security group allows port 80 from anywhere 0.0.0.0/0. ACL denies access to
port 80. Instance will not be able to access port 80 in/out from 0.0.0.0/0

### Disassociating Subnets
When you disassociate a subnet, it is re-associated with a default ACL

### Rules
- evaluates rules from lowest # to highest

### Best Practices
- increment rule #'s by 100

## DENY Specific Port Denies And ALLOW Large Port Range
Make sure to put the DENY rule BEFORE the large port range allow
ex. Rule 500 TCP Port:9923 0.0.0.0/0 DENY
    Rule 600 TCP Port:9000 to 65535 0.0.0.0/0 ALLOW

## Limitations
- do not affect traffic on cidr block 169.254.0.0/16
- can only be deleted if no subnets are associated with it
- default network acl cannot be deleted

