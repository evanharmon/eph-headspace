# AWS ELASTICACHE MEMCACHED

## SwapUseage
- should be 0 most of time, should not exceed 50Mb
- if over 50Mb, increase memcached_connections_overhead param

## memcached_connections_overhead
- amount of memory reserved for memcached connections and other misc overhead
