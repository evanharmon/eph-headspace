# AWS VPC BASIC BUILD STEPS

## Create VPC
Define IP Address Range
Auto-generates default ACL and Route Table

## Create Subnets
Diff Availability Zones (AZ)
3 subnets ex. 10.0.1.0/24, 10.0.2.0/24, 10.0.3.0/24

## Create Internet Gateway
Attach IGW to VPC

## Create Public Route Table
Adjust Public Subnet
Keep default routes to VPC CIDR block (10.0.0.0/16)
Allow HTTP, HTTPS, SSH to world (0.0.0.0/0) to target Internet Gateway (IGW)
Associate Route Table with Public Subnet

## Provision EC2 Instance In Public Subnet
Give it an Elastic IP address
Create SG allowing all access (0.0.0.0/0) to SSH and HTTP/HTTPS
Attach keypair

## Provision EC2 Instance In Private Subnet
no public IP address since it's Private
attach to SG group made when provisioning public subnet EC2 instance
in this setup, private instance will have NO internet access
