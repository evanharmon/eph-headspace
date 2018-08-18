# GRAPHQL CURL REQUESTS

## Simple Query
```
$ curl 'http://localhost:4000/graphql'\
    -H 'Content-Type: application/json'\
    -H 'Accept: application/json'\
    -d '{"query":"query { metadata { appName }}","variables":"{}"}'
```

## Query Function with Arguments
```
$ curl 'http://localhost:4000/graphql'\
     -H 'Content-Type: application/json'\
     -H 'Accept: application/json'\
     -d '{"query": "query { metadata(appName: \"test\"){ appName appVersion }}","variables":"{}"}'
```

## Query Multiple Resolvers for Nested Documents
```
$ curl 'http://localhost:4000/graphql'\
    -H 'Content-Type: application/json'\
    -H 'Accept: application/json'\
    -d '{"query": "query { permit(_id: \"test\"){ type } metadata(appName: \"test\"){ appName appVersion }}","variables":"{}"}'
```
