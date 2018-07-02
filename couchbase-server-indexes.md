# Queries Need indexes first - not auto created
`create primary index on `travel-sample``

# Delete Remove index
`drop index dbname.idxname`

# Create Index
`create index idxappname on dbname(doc.field)`

# Create index via CURL n1ql query
```
curl \
  -d 'statement=CREATE PRIMARY INDEX on mybucket' \
  http://localhost:8093/query
```

# Covered index on an array
# Article https://blog.couchbase.com/1-making-most-of-your-arrays-with-covering-array-indexes-and-more/
```
create index idx_functloc on mybucket(
  DISTINCT ARRAY n.Locs FOR n IN payload.myarray1 END,
  payload.myarray2
  )
WHERE type = "order"
and payload.myarray2 IS NOT MISSING
```

# another example
```
CREATE INDEX idx_type_div on mybucket(type, payload.Division)
WHERE type IS NOT MISSING
AND type = "order"
AND payload.Division IS NOT MISSING
USING GSI;
```
