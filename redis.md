# REDIS

Key / Value store

## Summary

Notes on working with Redis

## Resources

- [Command List](https://redis.io/commands)

### Default Port

6379

## Types

Values can be an int, a string, or a JSON object. So more than a single value
can be stored in a single key

### Less Recently Used (LRU) eviction

handle clearing keys to make room for new keys to stay with in maxMemory setting

## CLI

### Start

`redis-server`

### Check Redis

`redis-cli ping`

### Log In

`redis-cli`

## Shell

### General Commands

#### Shutdown

```console
shutdown save
shutdown nosave
```

#### Kill Connection

`CLIENT KILL addr:port`

#### Kill All Connections

`CLIENT KILL TYPE type normal`

### Key Commands

#### Check If Key Exists

```console
EXISTS city
```

#### Get All Keys

```console
KEYS *
```

#### Get Specific Prefix'd Keys

```console
KEYS koa:sess:*
```

#### Get Key

```console
GET koa:sess:<id>
```

#### Get Multiple Keys

```console
MGET street city
```

#### Get And Set

Returns previous value

```console
GETSET mykey myval
```

#### Set Key

```console
SET city dallas
```

#### Set Key And Expiration

```console
SET mykey EX 60
```

#### Set Multiple Values

```console
MSET street main city dallas
```

#### Delete

```console
DEL mykey
```

#### Increment

```console
INCR mycounter
```

#### Increment By

```console
INCRBY mycounter 100
```

#### Decrement

```console
DECR <key>
```

### TTL Commands

#### Set TTL Time Out

In seconds

```console
TTL mykey 60
EXPIRE mykey 5
```

### Hash Commands

similar to objects in javascript

### Get All Fields From Hash

```console
HGETALL myhash
```

#### Get Field From Hash

```console
HGET myhash myfield
```

#### Get Multiple Fields From Hash

```console
HGET myhash myfield1 myfield2 myfield3
```

#### Check If Field Exists In Hash

```console
HEXISTS myhash myfield1
```

#### Set Multiple Fields In Hash

Does Not Overwrite

```console
HMSET myhash field1 "Hello" field2 "World"
```

#### Edit Hash

Overwrites

```console
HSET myhash field1 "Hello"
```

#### Increment Field In Hash

```console
HINCRBY myhash myfield1 5
```
