# Log the query heading to couchbase server
## lib/bucket.js in the node_module
```
Bucket.prototype._n1qlReq = function(host, q, adhoc, emitter) {
  console.log('q ', q);
```

# Pass array IN clause in a query
## pass ids like so [ 'order-1234', 'order-1345' ]
```
SELECT
  doc.OrderNo as OrderNo,
  ARRAY_DISTINCT(doc.myarray[*].Group) as Groups
FROM mybucket AS doc
WHERE meta(doc).id IN ($1)
```

# N1QL example
## https://developer.couchbase.com/documentation/server/current/sdk/nodejs/n1ql-queries-with-sdk.html
```
var couchbase = require('couchbase');
var cluster = new couchbase.Cluster('couchbase://127.0.0.1');
var bucket = cluster.openBucket('default');
```
