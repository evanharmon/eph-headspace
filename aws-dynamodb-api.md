# AWS DYNAMODB API

## Headers
```
X-Amz-date
X-Amz-Target
Content-Type
Host
```

## BatchWriteItem
Max batch count is 25
Max request size 16mb

## BatchGetItem
Max batch count is 100
Single response limit of 16mb

## Query
Single response limit of 1mb

## Scan
Single response limit of 1mb, returns and tells you last evaluated key
