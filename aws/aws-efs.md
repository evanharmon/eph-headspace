# AWS ELASTIC FILE STORE

## Resources

[AWS Blog Best Practices Docker](https://aws.amazon.com/blogs/storage/best-practices-for-using-amazon-efs-for-container-storage/)
[AWS Blog Automate](https://aws.amazon.com/blogs/storage/automate-mounting-amazon-efs-file-systems-from-the-ec2-launch-instance-wizard/)

## Features

- supports NFSv4
- pay only for storage you use - no pre-provisioning required
- can scale up to petabytes
- data stored across multiple AZs
- supports thousands of concurrent NFS connections
- read after write consistency

## Use Case

file server - apply both file level and directory level permissions

## Port

open up port 2049
