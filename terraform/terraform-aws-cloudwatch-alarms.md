# TERRAFORM AWS CLOUDWATCH ALARMS

## Summary

Notes on using terraform with AWS Cloudwatch Alarms

## Resources

- [Resource Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_metric_alarm#datapoints_to_alarm)

### SQS Queue Alarm

Need to output name of SQS queue in terraform - not available on terraform resource outputs!

```hcl
resource "aws_sqs_queue" "terraform_queue" {
  name = "terraform-example-queue"
}

resource "aws_cloudwatch_metric_alarm" "oldest_message_age" {
  comparison_operator = "GreaterThanThreshold"
  metric_name         = "ApproximateAgeOfOldestMessage"
  namespace           = "AWS/SQS"
  period              = "300"
  statistic           = "Average"
  threshold           = "150"
  treat_missing_data  = "ignore"

  dimensions = {
    QueueName = aws_sqs_queue.terraform_queue.name
  }
}
```
