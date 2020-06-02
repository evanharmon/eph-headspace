# AWS VPC

## Summary

Notes on working with vpc's in AWS

## Resources

[DNS Support](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html#vpc-dns-support)

## Limitations

- allowed 5 VPCs Per Region
- allowed 200 Subnets Per VPC
- size of vpc CANNOT be changed after it is created
- max # of Security Groups per Instance is 5

## Deleting A VPC

all instances must be terminated first

## Availability Zones

names of AZs are randomly applied. 'eu-west-1b' may not be the same location
between different accounts

## EnableDnsHostnames and EnableDnsSupport

When both set to true:

- instances with a public IP address receive corresponding public DNS hostnames
- Amazon-provided DNS server can resolve Amazon-provided private DNS hostnames
