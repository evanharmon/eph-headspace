# AWS COST OPTIMIZATION PILLAR

## Summary

Notes on the AWS cost optimization pillar in the AWS Well-Architected
Framework

## Resources

## Definition

- matched supply and demand: auto scaling, lambda
- cost-effective resources: ec2 reserved instances, AWS Trust Advisor
- expenditure awareness: CloudWatch Alarms, SNS
- optimizing over time: AWS Blog, AWS Trusted Advisor

## Design Principles

- transparently attribute expenditure
- use managed services to reduce cost of ownership
- trade capital expense for operating expense
- benefit from economies of scale
- stop spending money on data center operations

## Best Practices

### Matched Supply And Demand

- optimally align supply with demand
- autoscaling, lambdas
- cloudwatch helps to keep track of demand

### Matched Supply And Demand Questions

How do you make sure your capacity matches but does not substantially exceed
How are you optimizing useage of AWS services?

### Cost-effective Resources

use the correct instance type - think hours running. t2 micro might end up more
expensive than a quick m4.2xlarge only running for a cpl minutes

### Cost-effective Resources Questions

Have you selected the appropriate resource types to meet your cost targets?
Have you selected the appropriate pricing model to meet your cost targets?
Are there managed services (higher-level services than EC2, EBS, and S3) that
you can use to improve your ROI?

### Expenditure Awareness

- use allocation tags to track by department, etc
- use consolidated billing
- use billing alerts

### Expenditure Awareness Questions

What access controls and procedures do you have in place to govern AWS costs?
How are you monitoring usage and spending?
How do you decommission resources that you no longer need, or stop resources
that are temporarily not needed?
How do you consider data-transfer charges when designing your architecture?

### Optimizing Over Time

Keep track of the changes made to AWS
Constantly re-evaluate your existing architecture
Subscribe to AWS blog
Use services like Trusted Advisor

### Optimizing Over Time Question

How do you manage and/or consider the adoption of new services?
