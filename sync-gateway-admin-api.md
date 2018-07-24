# SYNC GATEWAY ADMIN API

## API Admin Document Create
USE `PUT` not `POST`

## API ADMIN Delete
query string for rev
Example: `DELETE /{db}/{doc.id}?rev={doc.rev}`

## API Change Logging
```
$ curl -X PUT \
    --header 'Content-Type: application/json' \
    --header 'Accept: application/json' \
    -d 'CRUD' \
    'https://localhost:4985/_logging'
```

## API Start Continuous Replication
```
$ curl -v -w "\n" -X POST \
    --header 'Accept: application/json' \
    -d '{"replication_id":"my-test-replication","source":"travel-sample","target":"http://10.0.1.3:4985/travel-sample","continuous":true}' \
    http://localhost:4985/_replicate
```

## API Cancel replication
add ‘cancel’: true to json body
```
$ curl -v -w "\n" -X POST \
    --header 'Accept: application/json' \
    -d '{"replication_id":"my-test-replication","source":"customers","target":"http://localhost:4987/db","continuous":true, "cancel":true}' \
    http://localhost:4985/_replicate
```

## API Check Replications
`curl -v "http://localhost:4985/_active_tasks”`

## API Logging Bug
Logging SG-Replicate …. there is a bug in SG where you can not use the
REST _logging to turn off/on “Replicate” log level… you have to hard code it
in the config file right now

## API Get Conflicts
```
$ curl -X GET \
    'http://localhost:4985/db/_changes?active_only=true&style=all_docs'
```
