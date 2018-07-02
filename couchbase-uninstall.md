# Steps
```
$ /opt/couchbase/etc/couchbase_init.d stop
$ systemctl stop Couchbase-server.service
```

## To uninstall couchbase-sync-gateway:
`$ /opt/couchbase-sync-gateway/service/sync_gateway_service_uninstall.sh`

## Uninstall couchbase-server
`$ sudo rpm -e couchbase-server`
then go inside /opt/ to remove the remaining folders => rm -rf couchbase
