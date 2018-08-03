# SSH

[AWS Guide]
(http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)

## .SSH Folder
Make sure key file is in .ssh folder and has private permissions
`$ chmod 400 /path/my-key-pair.pem`

## Log in with Reference Key File
```
$ ssh -i $HOME/.ssh/my-key-pair.pem \
    ec2-user@ec2-54-0-0-123.compute-1.amazonaws.com
```

## OS X Port Forwarding
```
$ ssh-add -K mykeypair.pem
$ ssh -A ec2-user@54.0.0.123
```

## LINUX Port Forwarding
```
$ ssh-add -c mykeypair.pem
$ ssh -A ec2-user@54.0.0.123
```

## Generate Public Key from Private Key
```
$ ssh-keygen -y \
    -f ~/Downloads/mykeypair.pem \
    > ~/Downloads/mykeypair.pub
```

## Generate Public Key for Amazon from Private Key
`ssh-keygen -e -m RFC4716 -f ~/Downloads/mykeypair.pem`

## Generate User public key for SSH connections
```
$ cd $HOME/.ssh
$ ssh-keygen -t rsa -b 4096
```
