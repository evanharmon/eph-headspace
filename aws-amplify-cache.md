# AWS AMPLIFY CACHE

## Summary

Notes on working with the `Cache` package of aws-amplify in javascript

## Resources

- [Docs](https://aws-amplify.github.io/docs/js/cache)

## Set Expiration

```javascript
Cache.setItem('id', id, {
  expires: new Date(Date.now() + 1000 * 60 * 1), // 1 minute
})
```
