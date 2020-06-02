# SYNC GATEWAY CONFIG FILE

## GET File
`localhost:4985/_config`

## Example Configs (Dev only)
`$ cat examples/basic-sync-function.json`

## Production Config CI Example
Bootstrap config file via ansible, puppet
```
{
    adminInterface: '',
    interface: '',
    Logging: []
}
```
`PUT` from a central source to Sync_Gateway / LB's
Add in bucket passwords they stay in memory and are obfuscated

## `PUT` Config Example
Username is the database name
```
{
  "server": "walrus:",
    "pool": "default",
    "bucket": "sync_gateway",
    "name": "sync_gateway",
    "users": {
      "GUEST": {
        "name": "",
        "admin_channels": [
          "*"
        ],
        "all_channels": null,
        "usersname": "sync_gateway",
        "password": "passw0rd"
      }
    }
}
```

## Security Tips
Single Database - Single Bucket to keep data from being co-mingled

## Documentation
https://developer.couchbase.com/documentation/mobile/current/guides/sync-gateway/config-properties/index.html

## Cache Options
Depends how much you want to prevent the hop
- expiration (to keep from out of memory) - maybe 5 minutes for connected all
  the time
- if connected only sometimes - maybe 60 seconds

min & max # of documents
```
"cache": {
  "max_wait_pending": 0,
    "max_num_pending": 0,
    "max_wait_skipped": 0,
    "enable_star_channel": false,
    "channel_cache_max_length": 0,
    "channel_cache_min_length": 0,
    "channel_cache_expiry": 0
}
```

## Replication Config Example
Default for continuous is false
```
  "replications": [
    {
      "replication_id": "string",
      "source": "string",
      "target": "string",
      "continuous": false,
      "changes_feed_limit": "string",
      "filter": "string",
      "query_params": [
        "string"
      ]
    }
  ]
```

## Replication by channel
```
"filter":"sync_gateway/bychannel",
"query_params":["channel1","channel2"]
```

## Revs_limit
defaults to around 1000
