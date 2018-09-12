# GOLANG ARRAYS
Don't pass arrays in between functions. Expensive bc its a pass by value
operation

## Correct Way To Pass Array
```golang
process(&scores)

func process(arr *[3]int) error {}
```

## Create Pointer To Uninitialized Array
```golang
scores := new([]int)
```

## Make Initialized Array
```golang
scores := make([]int, 50)
```

## Declare Array
if the [] is empty then you are creating a slice instead
```golang
var names [3]*string
```

## Directly Assign To Array
```golang
*names[0] = "Evan"
```

## Create Two Dimensional Array
```golang
2dArray := [5][2]int{{1,10},{2,11},{3,14},{4,29},{5,30}}
```
