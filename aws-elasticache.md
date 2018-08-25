# AWS ELASTICACHE

## Concurrent Connections
if App is taking a long time to respond, check # that App is releasing
concurrent connections

## REDIS
single threaded

### Scaling / Evictions
to calc scale, take 90 and divide by # of cores
set threshold, can only scale out

### Monitoring Memory
no SwapUsage metric. Use reserved-memory

## MEMCACHED
multi threaded

### Scaling / Evictions
set threshold to 90%
scale up with more memory and / or scale out with more nodes

### SwapUseage
- should be 0 most of time, should not exceed 50Mb
- if over 50Mb, increase memcached_connections_overhead param

### memcached_connections_overhead
- amount of memory reserved for memcached connections and other misc overhead
