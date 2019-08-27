# YUM

## Summary

Notes on using yum

## Resources

[Cheat Sheet](https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf)

## Package manager for:

amazon linux, centos

## List Package Install

`$ yum list sudo`

## List ALL Installed Packages

`$ yum list installed`

## List Enable Software Respositories

```console
yum repolist
```

## Find Package

`$ yum search vim`

## Check for updates - dry run

`$ yum check-update`

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

## AMAZON LINUX

#### Install RPM's on Amazon Linux

https://aws.amazon.com/premiumsupport/knowledge-center/ec2-enable-epel/
`$ vim /etc/yum.repos.d/repel.repo`
change enabled=0 to enabled=1
BETTER METHOD
`$ sudo yum-config-manager --enable epel`

## Install GCC8 / Clang6 On Amazon Linux / RHEL / CENTOS

[STACK](https://unix.stackexchange.com/questions/477360/centos-7-gcc-8-installation)

```console
yum install -y scl-utils
yum install centos-release-scl
yum install devtoolset-8-gcc devtoolset-8-gcc-c++
scl enable devtoolset-8 -- bash
```
