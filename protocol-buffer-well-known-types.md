# PROTOCOL BUFFER WELL-KNOWN TYPES

## Timestamp
in seconds and nanoseconds
import is required
```
import "google/protobuf/timestamp.proto";

message customMessage {
  google.protobuf.Timestamp create_timestamp = 1;
}
```

## Duration
in seconds and nanoseconds
```
import "google/protobuf/timestamp.proto";
import "google/protobuf/duration.proto";

message customMessage {
  google.protobuf.Timestamp create_timestamp = 1;
  google.protobuf.Duration time_since_creation = 2;
}
```
