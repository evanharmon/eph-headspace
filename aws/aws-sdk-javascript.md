# AWS SDK JAVASCRIPT

## Summary

Notes on working with the javascript aws sdk

## Resources

- [AWS Docs](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/)
- [v4 Sign Docs](https://docs.aws.amazon.com/general/latest/gr/signature-v4-examples.html#signature-v4-examples-javascript)

## Retrieve Credentials

```javscript
const creds = AWS.Config.credentials.get()
```

## V4 Request Signing

- [Axios V4 signed request](https://medium.com/@joshua.a.kahn/calling-amazon-api-gateway-authenticated-methods-with-axios-and-aws4-6eeda1aa8696)

## Paginated Call

```javascript
async function listFunctions(id, maxResults = 25) {
  let list = []
  const params = { apiId: id, maxResults }
  try {
    while (true) {
      const res = await appsync.listFunctions(params).promise()
      list = list.concat(res.functions)
      if (null === res.nextToken) {
        break
      } else {
        params.nextToken = res.nextToken
      }
    }
  } catch (e) {
    return Promise.reject(e)
  }

  return Promise.resolve(list)
}
```
