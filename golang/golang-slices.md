# GOLANG SLICES
[Blog](https://blog.golang.org/slices)

## Pseudo Struct Example For Slices
```c
struct Slice {
  addr     *[]int
  length   int
  capacity int
}
```

## Passing Slices
Pass around slices instead of pointers. Easier to work with and very cheap

## General About Slices
NOT an array
slice describes a piece of an array

## Slice Headers
Contents of a slice can be edited but NOT the header
Copy of header is sent, must return a result parameter to affect header
```golang
func SubtractOneFromLength(slice []byte) []byte { }
```

## Create A Slice
```golang
mySlice := make([]int, 10)
```

## Create Slice With Max Capacity
```golang
mySlice := make([]int, 10, 15)
```

## Fail Slice
this creates an array instead
```golang
var names [3]*string
```

## Beware Creating Slices From Slices
[Blog](https://blog.golang.org/go-slices-usage-and-internals)
