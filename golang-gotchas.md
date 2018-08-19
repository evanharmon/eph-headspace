# GOLANG GOTCHAS

## Multiple Value In Single-Value Context
`a := json.Marshal(variable)`
needs to be
`a, _ := json.Marshal(variable)`

## EOF error on request
Means the request body is empty
