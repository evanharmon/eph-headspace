# AWS DYNAMODB CLI

## Variables

Entered with colon
`--key-condition-expression "station_id=:id"`
`--expression-attribute-values '{ "id": { "S": "1" }}'`

## GetItem

`$ aws dynamodb get-item --table-name mytable --key file://key.json`
or

```
$ aws dynamodb get-item \
    --table-name note \
    --key '{ "id": {"S": "1"}, "author": {"S": "Evan Harmon"} }'
```

## Describe Table

`$ aws dynamodb describe-table --table-name mytable`

## Table Scan

`$ aws dynamodb scan --table-name mytable`

## Create Table

`aws dynamodb create-table --cli-input-json file://table.json`

### CLI Skeleton JSON

only include attribute definitions for keySchema

```json
{
  "AttributeDefinitions": [
    {
      "AttributeName": "",
      "AttributeType": ""
    }
  ],
  "TableName": "",
  "KeySchema": [
    {
      "AttributeName": "",
      "KeyType": ""
    }
  ],
  "LocalSecondaryIndexes": [
    {
      "IndexName": "",
      "KeySchema": [
        {
          "AttributeName": "",
          "KeyType": ""
        }
      ],
      "Projection": {
        "ProjectionType": "",
        "NonKeyAttributes": [""]
      }
    }
  ],
  "GlobalSecondaryIndexes": [
    {
      "IndexName": "",
      "KeySchema": [
        {
          "AttributeName": "",
          "KeyType": ""
        }
      ],
      "Projection": {
        "ProjectionType": "",
        "NonKeyAttributes": [""]
      },
      "ProvisionedThroughput": {
        "ReadCapacityUnits": 3,
        "WriteCapacityUnits": 3
      }
    }
  ],
  "BillingMode": "PAY_PER_REQUEST",
  "ProvisionedThroughput": {
    "ReadCapacityUnits": 3,
    "WriteCapacityUnits": 3
  },
  "StreamSpecification": {
    "StreamEnabled": false
  },
  "SSESpecification": {
    "Enabled": true,
    "SSEType": "AES256",
    "KMSMasterKeyId": ""
  }
}
```
