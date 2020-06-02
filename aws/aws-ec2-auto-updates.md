# AWS EC2 AUTO UPDATES

## Install yum-cron
`$ sudo yum install -y yum-cron`

## Setup Updates
(https://jonathansblog.co.uk/yum-cron)
`$ vi /etc/yum/yum-cron.config`

## Add And Start Cron Service
```
$ chkconfig --add yum-cron
$ service yum-cron start
```
