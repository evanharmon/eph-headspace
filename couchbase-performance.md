# Couchbase Server has TTL
## cbLite has TTL - but has to be set by application
hard deletes - gone gone gone

# TTL's
reset TTL's on touches too

# Purge
frees up storage space

# 20meg limit on JSON for body history

# Server - check performance stats
`$ ./cbstats localhost:11210 timings -b db5 | less`
