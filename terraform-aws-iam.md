# TERRAFORM AWS IAM

## Summary

Notes on using terraform with AWS IAM service

## Attach Managed Policy To Role

[SO](https://stackoverflow.com/questions/45002292/terraform-correct-way-to-attach-aws-managed-policies-to-a-role)

```
data "aws_iam_policy" "ReadOnlyAccess" {
  arn = "arn:aws:iam::aws:policy/ReadOnlyAccess"
}
resource "aws_iam_role_policy_attachment" "sto-readonly-role-policy-attach" {
  role       = "${aws_iam_role.sto-test-role.name}"
  policy_arn = "${data.aws_iam_policy.ReadOnlyAccess.arn}"
}
```

## Potential Cause aws_iam_role Continually Updated

[GH Issue](https://github.com/hashicorp/terraform/issues/11873)
Multiple role policy attachments can clobber?
