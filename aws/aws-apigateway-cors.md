# AWS APIGATEWAY CORS

## Summary

Notes on handling CORS with api gateway

## Resources

- [Enabling Cors](https://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-cors.html)

### Enable Cors Options

- `Access-Control-Allow-Credentials` must be set to `'true'` with quotes

### Test Cors

#### Curl Call

```console
curl -v -X OPTIONS https://{restapi_id}.execute-api.{region}.amazonaws.com/{stage_name}
```
