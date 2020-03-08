# NODE URL

## Summary

Notes on working with URL objects in nodejs

## Resources

- [URL Docs](https://nodejs.org/api/url.html)

## URL Object Shape

```json
{
  href: 'https://id.appsync-api.us-east-1.amazonaws.com/graphql',
  origin: 'https://id.appsync-api.us-east-1.amazonaws.com',
  protocol: 'https:',
  username: '',
  password: '',
  host: 'id.appsync-api.us-east-1.amazonaws.com',
  hostname: 'id.appsync-api.us-east-1.amazonaws.com',
  port: '',
  pathname: '/graphql',
  search: '',
  searchParams: URLSearchParams {},
  hash: ''
}
```

## Create URL

```javascript
const { URL } = require('url')
const url = new URL('https://www.myapi.com/graphql')
```

## Parse Query Strings as well

```javascript
const url = URL.parse(res.headers.location, true)
```

# Create URL with only Path/query/search ending

```javascript
const url = URL.format({ pathname: /test/deinnopt, query: { user: '555' } })
```
