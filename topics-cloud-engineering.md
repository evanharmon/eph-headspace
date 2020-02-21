# TOPICS CLOUD ENGINEERING

## Summary

Topics for discussion with other cloud engineers

## Resources

## General Topics

### Cloud Services (AWS / AZURE / GCP)

- what cloud services have you worked with?
- have you worked in multi-cloud environments?

### Infrastructure as Code

- CloudFormation vs Terraform: strengths, weaknesses
- structuring / organizing IaC code / templates
- separating core infrastructure vs app infrastructure

#### CloudFormation

- experiences using cross-stacks vs child stacks

#### Terraform

- using TF in cross-account scenarios

### Containerization

- example CI / CD pipelines for Container Image Builds / Deployment
- when to use ECS / Docker Compose vs Kubernetes
- whare are the challenges involving docker compose and microservices?

### Microservices

- preferred communication style
- preferred api formats? GRAPHQL / GRPC / rest
- use of batch pipelines / workers

### Authentication / Authorization

- Cognito experiences?
- Auth0?

### Continuous Integration / Deployment

- preferences on CD in to production environments

## Advanced Topics

### Cross Account Log Consolidation

- describe strategy for aggregating multi-account logs in to one account with query support
- must include s3 / cloudtrail / vpc flow logs

### VPC Endpoints

- when to use them?
- how to determine if the endpoint is being used on lambda / ec2?
- any changes needed in SDK calls?
