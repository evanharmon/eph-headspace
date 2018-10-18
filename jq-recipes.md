## Query Example
`{ "results": [{ "doc": {} }] }`

`cat file.json | jq '.results[].doc'`

## Exclude Keys Example
```
cat ~/Downloads/myfile.json |\
  jq '.results[].doc' |\
  jq 'del(._id, ._rev)' |\
  more
```

`jq 'del(._id, ._rev)'`

## Map And Filter Array Of JSON To Inner Object
`cat file.json | jq '.docs' | jq 'map(.payload)' | more`

## Exclude Keys But Keep Commas For Array Of Objects
```
cat new.json |\
  jq '.results' |\
  jq 'map(select(.doc != null) | .doc | del(._rev))' >\
  test.json
```

## Exclude Nulls So You Can Map
`cat file.json | jq '.results' | jq 'map(select(.doc != null) | .doc)' | more`

```
cat file.json |\
  jq '.results' |\
  jq 'map(select(.doc != null) | .doc | del(._id,._rev))' >\
  export.json
```

## Copy Deep Nested Object And Use As Outer Id
`{ "docs": [{ "payload": { "d": { "Field": "XYZ" } } }] }`

```
cat file.json |\
  jq '.docs' |\
  jq 'map(. + { id: .payload.d.FUNCTION_LOCATION })' |\
  more
```

## Convert Number To String
`jq '{ docs: map(. + { _id: ((.payload.OBJECTID|tostring) + "-" + .payload.LOCATION) }) }'`

## To Lowercase
```
cat myfile.json |\
     jq '.docs' |\
     jq 'map(. + { id: ("city-" + (.payload.WorkCity|ascii_downcase)) })' |\
     less
```

## Move Property Out Of A Nesting Level And Delete Parent Property
```
cat myfile.json |\
  jq 'map(. + { payload: .results[0] } | del(.d))' |\
  less
```

## Add New Object With Array Of Objects
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

## Parse and Get Length Of Key
`cat file.json | jq '.results' | jq 'map(select(.id != null)| .) | length'`

## Assign JQ Result To A Bash Variable
`FILE_SYSTEM_ID=$(aws efs describe-file-systems|jq '.FileSystems[0].FileSystemId)`

## Get List Of Properties
`cat myfile.json | jq 'map(keys) | add | unique'`

## Get Max Of A Key Value In Array
`cat myfile.json | jq 'map(.OrderNo) | max'`
