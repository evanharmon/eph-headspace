# JQ RECIPES

## Summary

Recipes for common tasks using the JQ cli tool

## Resources

- [JSON / JQ / CSV tutorial](https://programminghistorian.org/en/lessons/json-and-jq)
- [Cheat Sheet](https://gist.github.com/olih/f7437fb6962fb3ee9fe95bda8d2c8fa4)

## Query Example

`{ "results": [{ "doc": {} }] }`

`cat file.json | jq '.results[].doc'`

## Exclude Keys Example

```console
cat ~/Downloads/myfile.json |\
  jq '.results[].doc' |\
  jq 'del(._id, ._rev)' |\
  more
```

```console
jq 'del(._id, ._rev)'
```

## Map And Filter Array Of JSON To Inner Object

```console
cat file.json | jq '.docs' | jq 'map(.payload)' | more
```

## Exclude Keys But Keep Commas For Array Of Objects

```console
cat new.json |\
  jq '.results' |\
  jq 'map(select(.doc != null) | .doc | del(._rev))' >\
  test.json
```

## Exclude Nulls So You Can Map

```console
cat file.json | jq '.results' | jq 'map(select(.doc != null) | .doc)' | more
```

```console
cat file.json |\
  jq '.results' |\
  jq 'map(select(.doc != null) | .doc | del(._id,._rev))' >\
  export.json
```

## Copy Deep Nested Object And Use As Outer Id

`{ "docs": [{ "payload": { "d": { "Field": "XYZ" } } }] }`

```console
cat file.json |\
  jq '.docs' |\
  jq 'map(. + { id: .payload.d.FUNCTION_LOCATION })' |\
  more
```

## Convert Number To String

```console
jq '{ docs: map(. + { _id: ((.payload.OBJECTID|tostring) + "-" + .payload.LOCATION) }) }'
```

## To Lowercase

```console
cat myfile.json |\
     jq '.docs' |\
     jq 'map(. + { id: ("city-" + (.payload.WorkCity|ascii_downcase)) })' |\
     less
```

## Move Property Out Of A Nesting Level And Delete Parent Property

```console
cat myfile.json |\
  jq 'map(. + { payload: .results[0] } | del(.d))' |\
  less
```

## Add New Object With Array Of Objects

```console
cat myfile.json |\
    jq '.results' |\
    jq 'map(select(.doc != null)|.doc)' |\
    jq 'map(. + { orgs: [{ orgType: "Placeholder" } + .orgsData[0].myfield] } | del(.orgsData))' |\
    less
```

## Map object and extra two properties to CSV

```console
cat myfile.json |\
     jq '.results' |\
     jq 'map(select(.doc != null) | .doc.payload | { field1: .field1, field2: .field2 })' |\
     jq -r '(map(keys) | add | unique) as $cols | map(. as $row | $cols | map($row[.])) as $rows | $cols, $rows[]' |\
     jq -r @csv > myfile.csv
```

## JSON Newline to CSV

```console
jq -rs '.[]|[.User, .CreateTimeStamp]|@csv'
```

## Parse and Get Length Of Key

```console
cat file.json | jq '.results' | jq 'map(select(.id != null)| .) | length'
```

## Assign JQ Result To A Bash Variable

```console
FILE_SYSTEM_ID=$(aws efs describe-file-systems|jq '.FileSystems[0].FileSystemId)
```

## Get List Of Properties

```console
cat myfile.json | jq 'map(keys) | add | unique'
```

## Get Max Of A Key Value In Array

```console
cat myfile.json | jq 'map(.OrderNo) | max'
```

## Get AMI ID From Packer Manifest.json

```console
cat manifest.json | jq '.builds | last | .artifact_id | split(":") | last'
```

## Read Directly From File

```console
jq -n --slurpfile f manifest.json '$f[]|.builds | last | .artifact_id | split(":") | last'
```

## Search For Word In Array

- [GH Issue](https://github.com/stedolan/jq/issues/861)

```console
jq '.arrayOfStuff[] | select(.key2 | contains("dar"))' JSONFile.json
```

## Wrap Items In Array And Add Commas

- [GH Issue](https://github.com/stedolan/jq/issues/124)

```console
jq -r '[.Items]' test.json
```

## Create Valid JSON From Newline-Delimited JSON

```console
jq -rs '.' my-newline-json.json
```

## Use Env Variable

```console
jq '.Messages | map(. + { Id: .MessageId, MessageBody: .Body } | del(.Body,.MD5OfMessageAttributes,.MD5OfBody,.ReceiptHandle,.Attributes,.MessageId)) | { QueueUrl: env.Q_URL, Entries: . }' messages.json > cli-input.json
```

## Convert Newline Delimited Text To Array

```console
jq -rs '.' myfile.txt
```

## Newline JSON

### Get Length Of Newline JSON

```console
jq -rs '.|flatten' myfile.json
```

### Flatten NewLine Array JSON

```json
["one", "two", "three"][("four", "five", "six")]
```

```console
jq -rs '.|flatten' myfile.json > flattened-myfile.json
```
