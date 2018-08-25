# AWS CODE DEPLOY

## Troubleshooting
### ApplicationStop Keeps Failing
launch from cli with `--ignore-application-stop-failures`

### YAML File Does Not Exist
try triggering code pipeline again after the initial firing - yaml file wasnt
recognized yet

### Error Cannot Assume Role Provided
Need to setup trust relationship with codedeploy
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "",
      "Effect": "Allow",
      "Principal": {
        "Service": "codedeploy.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
