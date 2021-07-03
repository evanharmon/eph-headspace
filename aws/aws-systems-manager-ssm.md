# AWS SYSTEMS MANAGER

## Summary

Notes on using the services provided by AWS Systems Manager

## Resources

- [CF Template To Debug Instances Not Joining SSM](https://aws.amazon.com/blogs/mt/reporting-and-remediating-ec2-instances-that-aws-systems-manager-doesnt-list-as-managed-instances/)
- [AWS Blog Session Manager](https://aws.amazon.com/blogs/mt/vr-beneficios-session-manager/)

## Run Docker Commands

Must switch to root user first. For ECR permissions, i've found it easiest to
export key / secret / session token which is a temporary cred for my admin user

```console
sudo su
docker image ls
```
