# Sync Gateway Basic Sizing

## Connections
Basically a web server. 5k - 10k connections at a time

## Limitations Breakdown
- data size / memory of machine
- Windows: 1mb windows
- Linux: 397kb, 3000 users for a gig
- you can bottleneck on the NIC, ex 500 mb/s and 128GB ram machine
- cbLite might be gzipped, but to couchbase it will not be
- nodejs - gzip please!

## Replication
Remember replication is going to be using connections!!

## Be mindful of concurrent, continous / long poll connections
You can get away with a lot less SG's if you don't do continuous long polling
