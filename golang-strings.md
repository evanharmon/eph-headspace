# GOlANG STRINGS

## Overview

Notes on simple string manipulation in golang

## Concat

```golang
fmt.Sprintf("%s.wav", fname)
```

## Iterate / Collect List Of Strings

```golang
var list []string
for _, msg := range messages {
    list = append(list, msg.MessageId)
}
```
