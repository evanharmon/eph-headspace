# TERRAFORM NAMING AND SORTING

## Summary
Naming and sorting conventions while terraforming planets in the Milky Way
Galaxy. Or using Hashicorp's Terraform for Infrastructure as Code.

## Naming

## Sorting

#### Alphabetical To A Point
It is tempting to rigidly sort terraform object properties alphabetically like
below.

```
resource "aws_autoscaling_notification" "autoscaling_group" {
  group_names = ["${aws_autoscaling_group.autoscaling_group.name}"]

  notifications = [
    "autoscaling:EC2_INSTANCE_LAUNCH",
    "autoscaling:EC2_INSTANCE_LAUNCH_ERROR",
    "autoscaling:EC2_INSTANCE_TERMINATE",
    "autoscaling:EC2_INSTANCE_TERMINATE_ERROR",
  ]

  topic_arn   = "${aws_sns_topic.autoscaling_group.arn}"
}
```
~~Don't~~ it will lead to lots of extra lines in your terraform files. This
happens because of the Terraform auto formatter. I agree with the auto
formatter on the extra lines for readability.

Group single line properties together, and multi-line objects below the
single-line properties.

```
resource "aws_autoscaling_notification" "autoscaling_group" {
  group_names = ["${aws_autoscaling_group.autoscaling_group.name}"]
  topic_arn   = "${aws_sns_topic.autoscaling_group.arn}"

  notifications = [
    "autoscaling:EC2_INSTANCE_LAUNCH",
    "autoscaling:EC2_INSTANCE_LAUNCH_ERROR",
    "autoscaling:EC2_INSTANCE_TERMINATE",
    "autoscaling:EC2_INSTANCE_TERMINATE_ERROR",
  ]

}
```
