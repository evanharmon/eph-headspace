# AWS EC2 GOTCHAS

## Can't SSH - Permission Denied (publickey)
On your macbook pro, make sure you've done `ssh-add -K ~/.ssh/key_pair.pem`
You can also edit ~/.ssh/config like so to avoid having to do
`ssh -A -i ~/.ssh/key_pair.pem `
```
Host 107.*...
    ForwardAgent yes
    IdentityFile ~/.ssh/key-pair.pem
```
## AWS
Also make sure you are not in ROOT when you logged in to ec2-user. ec2-user will
have the environment ssh creds to forward but not root account

## Curl Connection Refused
Make sure you are doing full url for localhost
`$ curl -v http://localhost:4985/_admin`

## Free Tier EC2
t2.micro
