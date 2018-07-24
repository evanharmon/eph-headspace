# SYNC GATEWAY VIEWS

## Limitations
Only one dynamic parameter available for the Query string

## Key Query String
On a view, the key should be the value of a field you want to filter on

## Example
```
curl -X PUT \
  http://localhost:4985/mybucket/_design/myapp \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
    "views": {
      "myparam": {
        "map": "function (doc, meta) {\n if (doc.OrderType === '\''GROUND'\'') {\n emit(doc.payload.OrderNo, doc.payload.data);\n}\n}"
      }
    }
  }'
```

# Get View by Key
`http://localhost:4984/mybucket/_design/myapp/_view/myparam?key=%22000016%22`
