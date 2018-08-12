# NODE URL

## Parse Query Strings as well
`const url = URL.parse(res.headers.location, true);`

# Create URL with only Path/query/search ending
`const url = URL.format({ pathname: /test/endpoint, query: { user: '555' } });`
