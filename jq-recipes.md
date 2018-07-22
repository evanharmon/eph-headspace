## Query Example
`{ "results": [{ "doc": {} }] }`

`cat file.json | jq '.results[].doc'`

## Exclude keys example
```
cat ~/Downloads/myfile.json |\
  jq '.results[].doc' |\
  jq 'del(._id, ._rev)' |\
  more
```

`jq 'del(._id, ._rev)'`

## Map and Filter array of JSON to inner object
`cat file.json | jq '.docs' | jq 'map(.payload)' | more`

## Exclude keys but keep commas for array of objects
```
cat new.json |\
  jq '.results' |\
  jq 'map(select(.doc != null) | .doc | del(._rev))' >\
  test.json
```

## Exclude nulls so you can map
`cat file.json | jq '.results' | jq 'map(select(.doc != null) | .doc)' | more`

```
cat file.json |\
  jq '.results' |\
  jq 'map(select(.doc != null) | .doc | del(._id,._rev))' >\
  export.json
```

## Copy deep nested object and use as outer id
`{ "docs": [{ "payload": { "d": { "Field": "XYZ" } } }] }`

```
cat file.json |\
  jq '.docs' |\
  jq 'map(. + { id: .payload.d.FUNCTION_LOCATION })' |\
  more
```

## convert number to string
`jq '{ docs: map(. + { _id: ((.payload.OBJECTID|tostring) + "-" + .payload.LOCATION) }) }'`

## to lowercase
```
cat myfile.json |\
     jq '.docs' |\
     jq 'map(. + { id: ("city-" + (.payload.WorkCity|ascii_downcase)) })' |\
     less
```

## Move property out of a nesting level and delete parent property
```
cat myfile.json |\
  jq 'map(. + { payload: .results[0] } | del(.d))' |\
  less
```

## Add new object with array of objects
```
cat myfile.json |\
    jq '.results' |\
    jq 'map(select(.doc != null)|.doc)' |\
    jq 'map(. + { orgs: [{ orgType: "Placeholder" } + .orgsData[0].myfield] } | del(.orgsData))' |\
    less
```

## Map object and extra two properties to CSV
```
cat myfile.json |\
     jq '.results' |\
     jq 'map(select(.doc != null) | .doc.payload | { field1: .field1, field2: .field2 })' |\
     jq -r '(map(keys) | add | unique) as $cols | map(. as $row | $cols | map($row[.])) as $rows | $cols, $rows[]' |\
     jq -r @csv > myfile.csv
```

## Parse and get length of key
`cat file.json | jq '.results' | jq 'map(select(.id != null)| .) | length'`

## Assign JQ result to a bash variable
`FILE_SYSTEM_ID=$(aws efs describe-file-systems|jq '.FileSystems[0].FileSystemId)`

## Get list of properties
`cat myfile.json | jq 'map(keys) | add | unique'`

## Get Max of a key value in array
`cat myfile.json | jq 'map(.OrderNo) | max'`
