# NODE REDIS
(https://github.com/NodeRedis/node_redis)

# Client Setup
```
const rclient = redis.createClient({
   host: config.redis.host,
   port: config.redis.port,
   auth_pass: config.redis.pass
});
```
