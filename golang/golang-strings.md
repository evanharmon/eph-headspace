# GOlANG STRINGS

## Overview

Notes on simple string manipulation in golang

## Quick Concat

```golang
fmt.Sprintf("%s.wav", fname)
```

## Convert []string To String

- [Docs](https://golang.org/pkg/strings/#Join)
- [SO](https://stackoverflow.com/questions/41756412/golang-convert-type-string-to-string)

```golang
stringArray := []string {"Hello","world","!"}
justString := strings.Join(stringArray," ")
fmt.Println(justString)
```

## Iterate / Collect List Of Strings

```golang
var list []string
for _, msg := range messages {
    list = append(list, msg.MessageId)
}
```

## String Pointer

```golang
myStr := "test"
strPnt := &mystr
```

## Dereference String Pointer

```golang
func DerefString(s *string) string {
    if s != nil {
        return *s
    }

    return ""
}
```

## Convert String to Bytes

easy!

```golang
myStr := "Test"
b := []byte(myStr)
```
