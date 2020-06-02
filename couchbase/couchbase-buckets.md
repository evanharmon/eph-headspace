# API create / load sample bucket
```
curl -v -u Administrator:password -d '["travel-sample"]' \
    http://127.0.0.1:8091/sampleBuckets/install
```

# API Get Bucket Memory Quota
http://localhost:8091/pools/default/buckets/travel-sample

# API Change Bucket Memory Quota
```
$ curl -X POST -u [admin]:[password] \
 -d ramQuotaMB=[value] -d authType=[none | sasl] \
 -d proxyPort=[port]
 http://[localhost]:8091/pools/default/buckets/[bucket-name]
```

# CLI Create Bucket
```
couchbase-cli bucket-create -c 192.168.0.1:8091 \
       --bucket=test_bucket \
       --bucket-type=couchbase \
       --bucket-port=11222 \
       --bucket-ramsize=200 \
       --bucket-replica=1 \
       --bucket-priority=low \
       --wait \
       -u Administrator \
       -p password
```
