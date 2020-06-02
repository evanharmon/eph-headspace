# AWS SNS

## Summary

Notes on working with aws SNS service.
Push Notifications for Apple, Google, Fire OS, and Windows devices
set up, operate, send notifications from the cloud

## Delivery Options

SMS text message
Email
SQS
Lambda functions

## Topics

- like an 'access point' allows recipients to dynamically subscribe for
  identical copies of the same notification
- a topic can support deliveries to multiple endpoint types at the same time:
  ie. SMS, email, iOS

## AZs

SNS messages stored across multiple AZs

## SNS Benefits

- push-based delivery (no polling)
- inexpensive, pay as you go
- web-based AWS mgmt console use as well

## Pricing

$0.50 per 1 million
then $0.06 per 100,000 deliveries over HTTP
then $0.75 per 100 deliveries over SMS
then $2.00 per 100,000 deliveries over Email

## SNS vs SQS

SNS - Push
SQS - Polls (Pulls)
