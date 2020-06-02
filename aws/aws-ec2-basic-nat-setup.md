# AWS EC2 BASIC NAT SETUP
Start by performing steps in Basic VPC Build Steps guide markdown file

## Create Security Group For NAT
- allow inbound connections for Public Subnet (10.0.1.0/24)
- allow Private Subnet (10.0.2.0/24) for HTTP/HTTPS
- allow outbound connections for HTTP/HTTPS

## Provision NAT Instance In Public Subnet
- assign EIP / Public IP addres
- disable Source/Destination CHECK!
- attach to NAT Security Group

## Set Up Route On Default VPC Subnet
Add route allowing all traffic (0.0.0.0/0) to go to target NAT instance
