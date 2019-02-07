# GOLANG RUNE STRINGS

## Convert string to array of runes

```golang
r := []rune(str)
```

## convert runes to strings

```golang
string([]rune)
```

## Convert Struct to a string

```golang
type note struct {}
a, _ := json.Marshal(note)
hstr := string(a)
```

## Alias for

```golang
int32
```

## Convert from string to byte to rune

```golang
r, _ := utf8.DecodeRune([]byte(arr[i]))
```

## Convert rune to string

```golang
string(rune)
```

## Convert int to string

```golang
ans = strconv.Itoa(int(i))
```

## Convert string to int

String, Base, Bitsize

```golang
strconv.ParseInt("10", 10, 8)
```

parse string array to int

```golang
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
