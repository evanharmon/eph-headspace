# AWS ELASTIC NETWORK INTERFACES

## Summary

Notes on working with aws elastic network interfaces (eni)

## Resources

- [AWS Max Interfaces By EC2 Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)
- [Trunking](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/container-instance-eni.html)
- [Find and Delete Lambda ENI](https://aws.amazon.com/premiumsupport/knowledge-center/lambda-eni-find-delete/)
- [AWS Support Tools Repo](https://github.com/awslabs/aws-support-tools)

## Lambda ENI Cannot Be Deleted
[KB Article](https://forums.aws.amazon.com/thread.jspa?messageID=968480)
Could have an event source mapping

```console
aws lambda list-event-source-mappings
aws lambda delete-event-source-mappings --uuid <THE UUID LISTED>
```
