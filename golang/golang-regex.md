# GOLANG REGEX

## Basic Example
"Bunch", "of", "strings"
```
reg, err := regexp.Compile("[\"]")
     if err != nil {
     log.Fatal(err)
}
s := reg.ReplaceAllString(strArr, "")
fmt.Printf("s is %v\n", s)
```

## Non-capture Group Between Brackets
`result := regexp.MustCompile(`(?:\[)(.*)(?:\])`).FindStringSubmatch(strArr)`

## Non-capture Group Between Double Quotes
`result2 := regexp.MustCompile(`(?:\")(.*)(?:\")`).FindStringSubmatch(strArr)`
