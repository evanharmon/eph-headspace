# GOLANG RUNE STRINGS

## Convert string to array of runes
`r := []rune(str)`

## convert runes to strings
`string([]rune)`

## Convert Struct to a string
```
type note struct {}
a, _ := json.Marshal(note)
hstr := string(a)
```

## Alias for
`int32`

## Convert from string to byte to rune
`r, _ := utf8.DecodeRune([]byte(arr[i]))`

## Convert rune to string
`string(rune)`

## Convert int to string
`ans = strconv.Itoa(int(i))`

## Convert string to int
String, Base, Bitsize
`strconv.ParseInt("10", 10, 8)`

parse string array to int
```
nArr := make([]int, len(sArr))
for i := 0; i < len(sArr); i++ {
     num, err := strconv.Atoi(sArr[i])
     if err != nil {
          log.Fatal(err)
     }
     nArr[i] = num
}

fmt.Printf("nArr is %v\n", len(nArr))
```
