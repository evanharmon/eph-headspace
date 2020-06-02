# SYNC GATEWAY PUBLIC API

## API PUBLIC POST Document Create
### if already exists - updates
```
$ curl -v -w "\n" \
    --header "Content-Type: application/json" \
    -d '{ "data": "data" }' \
    http://localhost:4984/travel-sample/
```

## API PUBLIC `PUT` Document Update
Creates if does not exist, use if you want to provide the _id value
```
http://localhost:4984/travel-sample/airline_44
{ data: 'data' }
```

## 412 Database Already Exists
Duplicate Database, need to put in id field, must have _rev in body
```
http://localhost:4984/travel-sample/airline_44
{ "id": "airline_44", "_rev": "1-7bb256b81e8c34d4de5f3163ca33a3fa", "data": "data" }
```

## API Check config
```
$ curl -X GET \
    --header 'Accept: application/json' \
    'https://localhost:4985/_config'
```

## API all docs call with cookie session key
```
$ curl -X GET \
    -H 'Accept: application/json' \
    --cookie 'SyncGatewaySession=xx...' \
    http://example.com/sync_gateway/_all_docs -v
```

## Example POST Body to Create a Document With a Specific ID
```
{
      "_id": "my-predictable-id",
      "doc": {}
}
```
