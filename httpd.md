# HTTPD

## Config File Location
`/etc/httpd/conf/httpd.conf`

## Start / Stop / Etc
```console
$ httpd -k start
```
or
```console
$ apachctl -k start
```

## Override Config And Start On Specific Port
```console
`$ httpd -c "listen 8080"`
```

## Check What Port Httpd Is Running On
```console
`$ netstat -anp |grep 80`
```

## Kill HTTPD
Only way i've found to do this is to kill the process id
