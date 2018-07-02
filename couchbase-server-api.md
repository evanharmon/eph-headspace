# API Init Node Server Memory Settings
```
$ curl \
  -v http://127.0.0.1:8091/pools/default \
  -d memoryQuota=512 \
  -d indexMemoryQuota=512 \
  -d ftsMemoryQuota=512
```

# API Step 1 init node password
```
$ curl \
  -u Administrator:password \
  -v http://localhost:8091/nodes/self/controller/settings \
  -d 'data_path=%2Fopt%2Fcouchbase%2Fvar%2Flib%2Fcouchbase%2Fdata& \
  index_path=%2Fopt%2Fcouchbase%2Fvar%2Flib%2Fcouchbase%2Fdata'
```

# API Step 2 rename node
```
$ curl \
  -u Administrator:password \
  -v http://localhost:8091/node/controller/rename \
  -d 'hostname=127.0.0.1'
```

# API Step 3 Init Node Server services
```
$ curl -v \
  -d services=kv%2Cn1ql%2Cindex%2Cfts \
  http://127.0.0.1:8091/node/controller/setupServices
```

# API Step 4 Init Node API Server User Password Port
# Usually last step
```
$ curl -v \
  -d port=8091 \
  -d username=Administrator \
  -d password=password \
  http://127.0.0.1:8091/settings/web
```

# API Get Node Info
`$ curl -v -u Administrator:password http://10.1.1.3:8091/pools/nodes`

# API set Global secondary index settings
```
$ curl -X POST \
  -u 'Administrator:password' \
  -d 'indexerThreads=0' \
  -d 'logLevel=info' \
  -d 'maxRollbackPoints=5' \
  -d 'memorySnapshotInterval=200' \
  -d 'stableSnapshotInterval=5000' \
  -d 'storageMode=forestdb' \
  'http://localhost:8091/settings/indexes'
```

# Add node to cluster from a current cluster machine
```
$ curl -v \
  -u Administrator:password \
  -d 'hostname=10.1.1.4&user=Administrator&password=password&services=kv' \
  http://10.1.1.3:8091/controller/addNode
```
