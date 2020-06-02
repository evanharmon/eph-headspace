# AWS SECURITY WHITEPAPER

## Infrastructure as a Service (IaaS)
requires customer security configuration
os updates, security patches
EC2, VPC, S3, etc.

## AWS Managed Services
AWS handles security, updates, etc
RDS, Redshift, etc.

## Distributed Denial Of Service (DDoS)
AWS has proprietary techniques against DDoS attacks

## Man in the Middle (MITM)
Amazon EC2 AMIs auto generate new SSH certs on boot to prevent MITM Attacks

## Spoofed Network Traffic
EC2 instances cannot send spoofed network traffic

# Port Scanning
You must submit a request for permission to conduct vulnerability scans and
they must be limited to your own instances

# Packet Sniffing
A virtual instance running in promiscuous mode cannot receive/sniff traffic from
a diff virtual instance. EC2 not susceptible to ARP cache poisoning

# Access Keys
digitally signed requests to AWS APIs
crytpo hash created from secret key text
protects against in transit, and potential replay attacks
15 minute request length
HMAC-SHA256 used

# Key Pairs
SSH in to EC2 instances
CloudFront creation of signed URLs

# X.509 Certificates
Digitally sign SOAP requests to AWS APIs
SSL server certs for HTTPS

## Credentials
If credentials are lost/forgotten, they cannot be recovered / re-downloaded.
Have to create new

# Passwords
max 128 chars

# MFA
hardware and virtual supported
can be enforced on API usage as well

# Custom EC2
X.509 required for customized instance-backed AMI

# Secure HTTPS
several services use Elliptic curve Diffie-Hellman Ephemeral (ECDHE) protocol.
Provides Perfect Forward Secrecy with ephemeral keys

# Logs
AWS says are just as important as credentials / encrypted endpoints. CloudTrail
helps here
