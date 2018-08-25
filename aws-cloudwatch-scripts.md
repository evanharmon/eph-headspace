# AWS CLOUDWATCH SCRIPTS
(http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/mon-scripts.html)

## Amazon AMI
### Install / Download Scripts
```
$ sudo yum install -y perl-Switch perl-DateTime perl-Sys-Syslog \
    perl-LWP-Protocol-https
$ sudo su
$ mkdir /CloudWatch
$ cd /CloudWatch
$ curl -O \
    http://aws-cloudwatch.s3.amazonaws.com/downloads/CloudWatchMonitoringScripts-1.2.1.zip
$ unzip CloudWatchMonitoringScripts-1.2.1.zip
$ rm CloudWatchMonitoringScripts-1.2.1.zip
$ cd aws-scripts-mon
```

### Setup Steps
Verify scripts can communicate with CloudWatch
```
$ cd /CloudWatch/aws-scripts-mon/
$ ./mon-put-instance-data.pl --mem-util --verify --verbose
```
Manually test
`$ ./mon-put-instance-data.pl --mem-util --mem-used --mem-avail`

Create cron job
`$ vi /etc/crontab`

`*/5 * * * * root /CloudWatch/aws-scripts-mon/mon-put-instance-data.pl --mem-util --mem-used --mem-avail`
