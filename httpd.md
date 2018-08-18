# HTTPD

## Config File Location
`/etc/httpd/conf/httpd.conf`

## Start / Stop / etc
`$ httpd -k start`
or
`$ apachctl -k start`

## Override Config and Start on Specific Port
`$ httpd -c "listen 8080"`

## Check What Port httpd is Running On
`$ netstat -anp |grep 80`

## Kill HTTPD
Only way i've found to do this is to kill the process id
