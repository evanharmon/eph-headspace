# SYNC GATEWAY

## Port
`localhost:4984/sync_gateway`

## Start SG
`$ bin/sync_gateway`
or
`$ bin/sync_gateway examples/basic-couchbase-bucket.json`

## Start SG with couchbase server param
`$ sync_gateway config.json -url http://10.0.1.3:8091`

## Basic sync bucket policy
```
{
  "log": ["*"],
  "databases": {
    "db": {
      "server": "http://localhost:8091",
      "bucket": "airlines",
      "users": { "GUEST": { "disabled": false, "admin_channels": ["*"] } }
    }
  }
}
```

## Sync Function Versioning
grab from a repo and POST

## Data uploads to Couchbase
Always through sync gateway. NEVER expose couchbase server

## Reason to always go through sync-gateway
If you go thru SDK, you have to implement security yourself. Thru SG it is
handling access-control

## CORS support
```
{
  "log": ["HTTP", "HTTP+", "CRUD"],
  "adminInterface": "sync-gateway:4985",
  "CORS": {
    "Origin": ["*"],
    "Headers": ["Content-Type"]
  },
  "databases": {
    "beer-sample": {
      "import_docs": "continuous",
      "unsupported": {
        "replicator_2": true
      },
      "bucket": "beer-sample",
      "username": "Administrator",
      "password": "password",
      "server": "http://database:8091",
      "users": {
        "GUEST": {
          "disabled": false,
          "all_channels": ["*"],
          "admin_channels": ["*"]
        }
      }
    }
  }
}
```
