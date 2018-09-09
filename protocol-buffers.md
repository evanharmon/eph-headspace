# PROTOCOL BUFFERS
Handle defaults carefully. No way to know if data was missing or the value
is empty

## Naming Conventions / Style
[Style](https://developers.google.com/protocol-buffers/docs/style)
[Uber](https://github.com/uber/prototool/blob/dev/etc/style/uber/uber.proto)
Message names: CamelCase
Fields: lowercase, underscore_separated
Enum Fields: uppercase, underscore_separated

## Rename Fields
Ok to rename fields. Just don't change the tag number

## Reserve Fields
Cannot mix reserve fields and tags
```
reserved "first_name";
reserved "first_name", "last_name";
```

## Reserve Tags
Cannot mix reserve tags and fields
```
reserved 2;
reserved 1, 3, 5, 20 to 25;
```
## Scenarios

### What happens when code can't find a field?
Default value is used



