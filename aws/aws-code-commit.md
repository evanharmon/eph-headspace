# AWS CODE COMMIT

## Steps To Add HTTPS Git User
- create IAM user
- attach codecommit access policy
- generate HTTPS Git Credentials

## HTTPS Git Usage on Mac OS and Linux
[guide](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-https-unixes.html#setting-up-https-unixes-credential-helper)

```console
git config --local credential.helper '!aws codecommit credential-helper $@'
git config --local credential.UseHttpPath true
```

## Steps To Add SSH Git User
- create IAM user
- attach codecommit access policy
- copy `~/.ssh/id_rsa.pub` value and upload to IAM User tab 'security credentials'
- copy IAM user tab `security credentials` SSH Key ID for below
- add the below to your `~/.ssh/config` with SSH Key ID from above
```
Host git-codecommit.*.amazonaws.com
User Your-IAM-SSH-Key-ID-Here
IdentityFile ~/.ssh/Your-Private-Key-File-Name-Here
```

## SSH Git Usage on Mac OS and Linux
```console
git config --local core.sshCommand "ssh -F ~/.ssh/config"
```

## SSH Git Multiple AWS Accounts
You'll need a config file per account to allow the specific SSH Key ID to be used
```console
git config --local core.sshCommand "ssh -F ~/.ssh/my-custom-config"
```
