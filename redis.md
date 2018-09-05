# REDIS
Key / Value store

## Values
Values can be an int, a string, or a JSON object. So more than a single value
can be stored in a single key

## Start
`redis-server`

## Shutdown
```
shutdown save
shutdown nosave
```

## Default Port
6379

## Check Redis
`redis-cli ping`

## Log In
`redis-cli`

## Kill Connection
`CLIENT KILL addr:port`

## Kill All Connections
`CLIENT KILL TYPE type normal`

## Less Recently Used (LRU) eviction
handle clearing keys to make room for new keys to stay with in maxMemory setting

http://redis.io/commands
### Terms <key> and <myhash> seem to be interchangeable

## Get All Keys
`KEYS *`

## Get Specific Prefix'd Keys
`KEYS koa:sess:*`

## Get Key's value
`GET koa:sess:<id>`

## Create New Key - Does Not Overwrite Key
`HMSET myhash field1 "Hello" field2 "World"`

## Edit Key - Overwrites Key
`HSET myhash field1 "Hello"`

## Set TTL TimeOut
### Redis will delete after it expires
`TTL <key> 60 ## Seconds`

## Delete a Key
`DEL <key>`

## Increment a Key
good for things like login attempts
`INCR <key>`
