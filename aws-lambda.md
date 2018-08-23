# AWS LAMBDA
Compute service

## Use Cases
- event-driven compute service. Example changes to data in S3 bucket or dynamoDB
table
- compute service in response to HTTP requests using Amazon API Gateway or API
calls made using AWS SDK's

## Under the hood
run on containers
using shared EC2 instances
resource isolation
100ms Execution limits - for billing/timeouts

## Function Output
you have to persist data somewhere
- returned data is not stored
- events don't receive output

## Anatomy of Lambda App
Code/Dependencies
Event
Output

## Event Sources
Schedules
S3 events
DynamoDB streams
Kinesis streams
SNS topics
API Gateway
SDK invocation

## Limitations
lowest RAM setting is 128MB
up to 1536MB RAM
CPU scales with RAM increase

## Logs
shows memory allocated and memory actually used

# S3 Put sample template
change Records[].s3.bucket.name
adjust arn above it to match

change Records[].s3.key to file

## ID (Static)
every published version has an ID

## Qualifiers (Named Pointers)
You can move the qualifier around as 'prod'
default is $LATEST

## Create Qualifier
Create Alias action

## Cold Starts
not sure how relevant this is now
(https://www.reddit.com/r/aws/comments/49l91l/lambda_functions_in_vpc_cold_boot_times_of_10/)
Lambdas running inside a vpc have cold start problems
It takes extra time for an ENI to be configured
