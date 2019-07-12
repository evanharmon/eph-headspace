# AWS EKS

## Summary

Notes on using AWS EKS kubernetes service

## Requirements

[AWS IAM AUTHENTICATOR](https://docs.aws.amazon.com/eks/latest/userguide/install-aws-iam-authenticator.html)

## Resources

[Getting Started Console](https://docs.aws.amazon.com/eks/latest/userguide/getting-started-console.html)

## AWS CLI Configuration

set your `AWS_PROFILE` to your iam user that creates the EKS cluster.
`export AWS_PROFILE="myname"`

If you create the cluser user an assumed role, you'll have to set that up in
`/.aws/config`

## EKS Cluster Creation Via Console

Important on security / initial login on public access. It's limited to
IAM user / role used to create cluster on console

```
When an Amazon EKS cluster is created, the IAM entity (user or role) that creates the cluster is added to the Kubernetes RBAC authorization table as the administrator (with system:master permissions. Initially, only that IAM user can make calls to the Kubernetes API server using kubectl.
```

[Authorization fails or no such host](https://docs.aws.amazon.com/eks/latest/userguide/troubleshooting.html#unauthorized)

EKS cluster created via iam user

```console
aws eks update-kubeconfig --name cluster_name
```

EKS cluster created via assumed-role

```console
aws eks update-kubeconfig --name cluster_name --role-arn arn:aws:iam::aws_account_id:role/role_name
```

## Update Kube Config

```console
aws eks update-kubeconfig --name my-eks-cluster
```

## Unable To Connect

[VPC Required Setup](https://stackoverflow.com/questions/55510783/cant-access-eks-api-server-endpoint-within-vpc-when-private-access-is-enabled)

```
enableDnsSupport: true
enableDnsHostnames: true
```
