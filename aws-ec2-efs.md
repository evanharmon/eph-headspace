# AWS EC2 EFS

## Steps To Mount EFS Volume On EC2
```
$ sudo yum install -y nfs-utils
$ sudo mkdir -p /efs
$ sudo mount -t nfs -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2 fs-11111111.efs.us-east-1.amazonaws.com:/ /efs
```

## Automatically Mount EFS Volume On Reboot
`$ sudo vi /etc/fstab/`
add
```
fs-11111111.efs.us-east-1.amazonaws.com/:       /efs    nfs4    nfsvers=4.1,rsize=1048576,rsize=1048576,hard,timeo=600,retrans=2,_netdev 0 0
```
`$ sudo mount /efs`
