# SSH

[AWS Guide](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)

## .SSH Folder

Make sure key file is in .ssh folder and has private permissions

```console
chmod 400 /path/my-key-pair.pem
```

## Log in with Reference Key File

```console
ssh -i $HOME/.ssh/my-key-pair.pem \
  ec2-user@ec2-54-0-0-123.compute-1.amazonaws.com
```

## OS X Port Forwarding

```console
ssh-add -K mykeypair.pem
ssh -A ec2-user@54.0.0.123
```

## LINUX Port Forwarding

```console
ssh-add -c mykeypair.pem
ssh -A ec2-user@54.0.0.123
```

## Generate Public Key from Private Key

```console
ssh-keygen -y \
  -f ~/Downloads/mykeypair.pem \
  > ~/Downloads/mykeypair.pub
```

## Generate Public Key for Amazon from Private Key

```console
ssh-keygen -e -m RFC4716 -f ~/Downloads/mykeypair.pem
```

## Generate User public key for SSH connections

```console
cd $HOME/.ssh
ssh-keygen -t rsa -b 4096
```
