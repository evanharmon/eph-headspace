# CLI Node Init Server
`couchbase-cli node-init -c localhost:8091 -u Administrator -p password`

# Remove node from cluster
```
/opt/couchbase/bin/couchbase-cli rebalance \
  -c localhost:8091 \
  -u Administrator \
  -p password \
  --server-remove=10.1.1.3:8091
```

# cbdocloader
```
/opt/couchbase/bin/cbdocloader \
  -n 127.0.0.1:8091 \
  -u Administrator:password \
  -b mybucket /tmp/mybucket.zip
```
