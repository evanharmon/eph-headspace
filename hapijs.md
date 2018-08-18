# HAPIJS

## Basic Setup
```
const Hapi = require('hapi');

const server = new Hapi.Server();

server.connection({ port: 3000 });

server.route({
  method: 'POST',
  path: '/',
  handler: (request, reply) => {
    reply({
      result: 'success',
    }).code(200);
  },
});
```

## Max Default Payload
1048576 (1MB)
