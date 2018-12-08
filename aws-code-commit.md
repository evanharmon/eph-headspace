# AWS CODE COMMIT

## Steps To Add User
- create IAM user
- attach codecommit access policy
- generate HTTPS Git Credentials

## Usage on Mac OS and Linux
[guide](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-https-unixes.html#setting-up-https-unixes-credential-helper)

```console
git config --local credential.helper '!aws codecommit credential-helper $@'
git config --local credential.UseHttpPath true
```
