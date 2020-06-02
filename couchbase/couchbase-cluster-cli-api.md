# CLI Create or init a cluster
```
/opt/couchbase/bin/couchbase-cli cluster-init \
  -c 10.0.1.240:8091 \
  --cluster-username=Administrator \
  --cluster-password=password \
  --cluster-port=8080 \
  --services=data,index,query,fts \
  --cluster-ramsize=256 \
  --cluster-index-ramsize=256 \
  --cluster-fts-ramsize=256 \
  --index-storage-setting=memopt \
  -u Administrator \
  -p password
```

# CLI Join a Cluster / Add A node to cluster
```
/opt/couchbase/bin/couchbase-cli server-add \
  -c ${CouchbaseInstance1.PrivateIp}:8091 \
  --server-add=${CouchbaseInstance2.PrivateIp}:8091 \
  --server-add-username=Administrator \
  --server-add-password=password \
  --services=index \
  --index-storage-setting=memopt \
  -u Administrator \
  -p password
```

# API Join a cluster
```
curl \
  -u Administrator:password \
  -d 'clusterMemberHostIp=192.168.0.1' \
  -d 'clusterMemberPort=8091' \
  -d 'user=admin' -d 'password=password' \
  http://10.1.1.2:8091/node/controller/doJoinCluster
```

# API Get cluster info
`curl -u Administrator:password http://localhost:8091/pools`

# API Get cluster detailed info
`curl -u Administrator:password http://10.0.1.2:8091/pools/default`

# API Rebalance cluster with known
```
curl -v -u Administrator:password \
  -d 'knownNodes=ns_1@10.1.1.2,ns_1@10.1.1.3' \
  http://localhost:8091/controller/rebalance
```

# CLI Rebalance cluster
```
/opt/couchbase/bin/couchbase-cli rebalance \
  -c 127.0.0.1:8091 \
  -u Administrator \
  -p password
```
