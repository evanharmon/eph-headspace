# PROTO FILES
This is all proto3
[Google](https://developers.google.com/protocol-buffers/docs/proto3)

## Scalar Types
### Strings
```
string
```
### Boolean
```
bool
```

### Numbers
```
double, float, int32, int64, uint32, uint64, sint32, sint64, fixed32, fixed64, sfixed32, sfixed64
```

### Bytes - for everything else, just like golang
```
bytes
```

### Enums - use or finite fixed value lists
```
enum ShipMethod {
  UNKNOWN_SHIP_METHOD = 0;
  AIR = 1;
  GROUND = 2;
  SEA = 3;
}

ShipMethod ship_method = 1;
```

## Field Tags
numbers starting with 1

## Arrays
use the `repeated` keyword as in:
```
repeated Buckets bucket = 1
```

## Limitations
Use underscore format - no spaces in field names
format requires trailing semi-colon on field definitions
Field Tags 19000 thru 19999 reserved by Google - can't use
No optional or required fields - any field not provided gets a default value

## Comments
```
// TODO:...
```
multiline
```
/* TODO:...
 * list of things to do */
```
always comment `bytes` fields


## Default Values
all fields get default values if not specified
number formats
```
int32: 0
```
```
bool: false
```
```
string: ''
```
```
repeated: []
```
```
enum: first value
```

## Nested Types
```
message SearchResponse {
  message Result {
    string url = 1;
    string title = 2;
    repeated string snippets = 3;
  }
  repeated Result results = 1;
}
```

## Imports
use fully qualified dir from root of project

## No Parameters
service functions cannot have zero parameters for PROTO. Must use empty proto
object as below
```
service MyService {
  rpc Create(CreateParams) returns (Response) {}
}
message CreateParams {}
message Response {}
```
