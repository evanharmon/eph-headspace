# PROTOCOL BUFFER MAPS
in memory key value store
can't be repeated
order is not preserved

## Example
```
message customMessage {
  string id = 1;
  map<string, Readings> readings = 2;
}
```
