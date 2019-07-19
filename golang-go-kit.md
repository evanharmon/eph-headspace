# GOLANG GO KIT

## Go Run yields Undefined Errors

make sure you are including all go files
`go run main.go instrumentation.go logging.go service.go transport.go`

## Resources

[Napolux How To](https://dev.to/napolux/how-to-write-a-microservice-in-go-with-go-kit-a66)
[MEDIUM shijuvar](https://medium.com/@shijuvar/go-microservices-with-go-kit-introduction-43a757398183)

## Examples

Remember they are post requests - need to do post as JSON
`$ curl -XPOST -d'{"s":"hello, world"}' localhost:8080/uppercase`

## Transport Flow

Transports.go
Endpoints.go
Middleware.go

## Logging
Seeing `MISSING` message in logs? Remember to pass a variable if the logger is expecting one.


```golang
logger := log.NewJSONLogger(os.Stderr)
logger.Log("no .env file found, falling back to environment variables.", err)
```
