# YUM

## Summary

Notes on using yum

## Package manager for:

amazon linux, centos

## List Package Install

`$ yum list sudo`

## List ALL Installed Packages

`$ yum list installed`

## Find Package

`$ yum search vim`

## Check for updates - dry run

`$ yum check-update`

## Install RPM's on Amazon Linux

https://aws.amazon.com/premiumsupport/knowledge-center/ec2-enable-epel/
`$ vim /etc/yum.repos.d/repel.repo`
change enabled=0 to enabled=1
BETTER METHOD
`$ sudo yum-config-manager --enable epel`

## Install List Of Packages From File

[SO](https://unix.stackexchange.com/questions/47304/centos-install-packages-listed-in-a-text-file)

```bash
yum -y install $(cat filename cat | tr '\n' ' ')
```

## List All Available Group Packages

```console
yum grouplist
```

## Get Info On Group Package

```console
yum groupinfo "Development Tools"
```
