# AWS VPC ROUTES
All subnets automatically hooked up to main route table. Don't put a path in
public internet in the main route table

## EC2
Instances do NOT retain their private IP

## Auto-Assign Public IP
Only available on new network interface with device index eth0

## Aggregate Burst Network Traffic
- spread instances across multiple AZs to minimize traffic concentration and
maximize fault tolerance
- only go for Placement Groups if the above option doesn't help
