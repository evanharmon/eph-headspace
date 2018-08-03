# SERVERLESS SERVICES PATTERN
- Single lambda function handles ~4 jobs related via data model or shared
infrastructure dependency
- Multiple http endpoints - small router parse event body

## Benefits
Less lambda functions to manage
Some separation of concerns
Teams can work autonomously
Theoretically better performance by calling each lambda more regularly

## Drawbacks
Debugging slightly more complicated
Requires creating router
Bigger function sizes

## Example
All User data model operations performed from same lambda
