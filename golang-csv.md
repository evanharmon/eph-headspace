# GOLANG CSV

## Parse CSV Line To Array
```
r := csv.NewReader(strings.NewReader(result[1]))
var sArr []string
for {
     record, err := r.Read()
     if err == io.EOF {
          break
     }
     if err != nil {
          log.Fatal(err)
     }
     sArr = record
}
```
