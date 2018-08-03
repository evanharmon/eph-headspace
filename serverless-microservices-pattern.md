# SERVERLESS MICROSERVICES PATTERN
Each job or functionality is isolated in to a lambda function
Function handles single event

## Benefits
Total separation of concerns
Very agile and safe in production
Easy to debug
Autonomous and can push to prod independently

## Drawbacks
Lots of functions leads to big cognitive overhead that is hard to manage
Performance could be slower
Deployments will be slower
Could reach cloudformation template limit quickly
