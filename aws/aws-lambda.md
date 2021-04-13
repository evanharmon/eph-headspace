# AWS LAMBDA

## Summary

Compute service

## Resources

- [AWS Sample Events Published](https://docs.aws.amazon.com/lambda/latest/dg/eventsources.html#eventsources-api-gateway-request)
- [Unzip Large Files In Lambda With Streaming](https://medium.com/@johnpaulhayes/how-extract-a-huge-zip-file-in-an-amazon-s3-bucket-by-using-aws-lambda-and-python-e32c6cf58f06)
- [AWS Blog Improved VPC Networking](https://aws.amazon.com/blogs/compute/announcing-improved-vpc-networking-for-aws-lambda-functions/)
- [Configuration Docs](https://docs.aws.amazon.com/lambda/latest/dg/configuration-console.html)
- [Investigating Spikes](https://aws.amazon.com/blogs/compute/investigating-spikes-in-aws-lambda-function-concurrency/)
- [Environment Variable Use](https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html)

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
up to 3008MB RAM
CPU scales with RAM increase

```
Lambda allocates CPU power linearly in proportion to the amount of memory configured. At 1,792 MB, a function has the equivalent of one full vCPU (one vCPU-second of credits per second).
```

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
default is \$LATEST

## Create Qualifier

Create Alias action

## Cold Starts

not sure how relevant this is now
(https://www.reddit.com/r/aws/comments/49l91l/lambda_functions_in_vpc_cold_boot_times_of_10/)
Lambdas running inside a vpc have cold start problems
It takes extra time for an ENI to be configured

## Lambda Network Interfaces

- [Improved VPC Networking With Hyperplane ENIS](https://aws.amazon.com/blogs/compute/announcing-improved-vpc-networking-for-aws-lambda-functions/)
  means Lambda VPC now re-uses network interfaces reducing the chance of running
  out of customer owned vpc ip / eni's.
  Hyperplane ENIs are tied to `security group:subnet` combination

```
Your function scaling is no longer directly tied to the number of network
interfaces and Hyperplane ENIs can scale to support large numbers of concurrent
function executions
```

## Run Time Environment Variables

the below are reserved

```txt
_HANDLER – The handler location configured on the function.
_X_AMZN_TRACE_ID – The X-Ray tracing header.
AWS_REGION – The AWS Region where the Lambda function is executed.
AWS_EXECUTION_ENV – The runtime identifier, prefixed by AWS_Lambda_—for example, AWS_Lambda_java8.
AWS_LAMBDA_FUNCTION_NAME – The name of the function.
AWS_LAMBDA_FUNCTION_MEMORY_SIZE – The amount of memory available to the function in MB.
AWS_LAMBDA_FUNCTION_VERSION – The version of the function being executed.
AWS_LAMBDA_INITIALIZATION_TYPE – The initialization type of the function, which is either on-demand or provisioned-concurrency. For information, see Configuring provisioned concurrency.
AWS_LAMBDA_LOG_GROUP_NAME, AWS_LAMBDA_LOG_STREAM_NAME – The name of the Amazon CloudWatch Logs group and stream for the function.
AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_SESSION_TOKEN – The access keys obtained from the function's execution role.
AWS_LAMBDA_RUNTIME_API – (Custom runtime) The host and port of the runtime API.
LAMBDA_TASK_ROOT – The path to your Lambda function code.
LAMBDA_RUNTIME_DIR – The path to runtime libraries.
TZ – The environment's time zone (UTC). The execution environment uses NTP to synchronize the system clock.
```
