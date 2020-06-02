# HAPIJS

## Access Query Params
```
  handler: function (request, reply) {
  // access request’s query parameter
  var params = request.query

  reply()
  }
```

## Middleware on Every Route
place after `server.start()`
```
  server.ext({
  type: 'onRequest',
  method: authMiddleware,
  });
```

## Shortcircuit on Middleware
`reply().takeover()`

## Check Request URL
`request.url`
