# AWS ELASTIC LOAD BALANCERS

## In / Out of Service
dependent on health checks

## Subnets vs Availability Zones (AZs)
Always use Subnets property when working in a VPC

## Security Best Practice
use security groups instead of IPs where possible

## Classic Load Balancer
Layer 4 routing (TCP)

## Application Load Balancer
Layer 7 routing
Has Target Groups

## End User Browser Experience
Monitor the latency of the elb

## Metric For Scaling
SurgeQueueLength

## SSL Certificates
DOES NOT support multiple SSL certs to host multiple sites
