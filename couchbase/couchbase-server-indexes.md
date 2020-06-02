# Queries Need Indexes First
not auto created
`CREATE PRIMARY INDEX ON `travel-sample``

# Delete Remove Index
`DROP INDEX dbname.idxname`

# Create Index
`CREATE INDEX idxappname ON dbname(doc.field)`

# Create Index Via CURL n1ql Query
```
curl \
  -d 'statement=CREATE PRIMARY INDEX on mybucket' \
  http://localhost:8093/query
```

# Covered Index On An Array
[Article](https://blog.couchbase.com/1-making-most-of-your-arrays-with-covering-array-indexes-and-more/)
```
CREATE INDEX idx_functloc on mybucket(
  DISTINCT ARRAY n.Locs FOR n IN payload.myarray1 END,
  payload.myarray2
  )
WHERE type = "order"
and payload.myarray2 IS NOT MISSING
```

# Another Example
```
CREATE INDEX idx_type_div ON mybucket(type, payload.Division)
WHERE type IS NOT MISSING
AND type = "order"
AND payload.Division IS NOT MISSING
USING GSI;
```
