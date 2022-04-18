# AWS EVENTBRIDGE

## SUMMARY
Notes on using Eventbridge in AWS


## Resources
- [Docs](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-event-bus.html)

## Bus'
Create custom buses for third-party services. Use the default bus auto created for the account
for AWS services like lambda, etc.

## Default Bus Access
- [EB Cross Account](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-cross-account.html)

The default event bus in your AWS account only allows events from one account. 
default bus does support cross-account / org access to those events
