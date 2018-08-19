# GOLANG GO KIT

## Go Run yields Undefined Errors
make sure you are including all go files
`go run main.go instrumentation.go logging.go service.go transport.go`

## Examples
Remember they are post requests - need to do post as JSON
`$ curl -XPOST -d'{"s":"hello, world"}' localhost:8080/uppercase`

## Transport Flow
Transports.go
Endpoints.go
Middleware.go
