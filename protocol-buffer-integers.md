# PROTOCOL BUFFER INTEGERS
always make the first value `unknown` since it will be the default

## Negative Values
Don't use int32 or int64 bc they use 10 bytes space and are inefficient on
negative value encoding
Use sint32 and sint64 bc they use ZigZag

## Large Values
Use fixed32 for > 2^28 and fixed64 for > 2^56
