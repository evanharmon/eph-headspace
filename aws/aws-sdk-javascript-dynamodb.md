# AWS SDK JAVASCRIPT DYNAMODB

## Summary

Notes on using the javascript sdk with dynamodb

## Resources

- [CSV Import Tool](https://github.com/GorillaStack/dynamodb-csv-export-import)

## ValidExpection Error On Schema

`ValidationException: The provided key element does not match the schema`

No need to add the "S", etc type wrapper to the json KEY shape. Can be like
below

```javascript
const params = {
  Key: {
    id: '1234',
  },
}
```
