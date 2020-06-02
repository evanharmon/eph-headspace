# AWS VPC SUBNETS
1 Subnet = 1 AZ

## Instances In Public Subnets
Don't have internet access unless you give them an EIP (Elastic IP address) or
attach to an ELB (Elastic Load Balancer)

## Route Tables
- routing changes happen immediately
- subnet must be associated with a route table
- vpc main route table associated to each subnet by default if none specified

## ACLs
- subnet can only be assigned to one ACL at a time
- subnet must have be associated with a network ACL. Default ACL used if none associated

## IP Address Range
10.0.0.0 - 10.255.255.255 (10/8 prefix)
172.16.0.0 - 172.31.255.255 (172.16/12 prefix)
192.168.0.0 - 192.168.255.255 (192.168/16 prefix)

- between /28 and /16 cidr mask
- AWS allows public address range but does not recommend

## IP Collisions
Any subnet in a vpc overlapping with a home/corporate network will not be
reachable from that home/corp network

## IP Address Reserved For Aws
First 4 and last reserved
- 10.0.0.0 Network Address
- 10.0.0.1 VPC Router
- 10.0.0.2 Typically DNS Server
- 10.0.0.3 Reserved for future use
- 10.0.0.255 broadcast not supported so it's unavailable as a port
