# GOLANG ITERATORS

## For Range
```golang
for _, e := range os.Environ() {
    pair := strings.Split(e, "=")
    fmt.Println(pair[0])
}
```

### Iterating Array Of Strings
must reference both return variables from `for ... range`. First variable
returned is of type int (index)
```golang
envs := []string{"GOOGLE_PROJECT_ID", "GOOGLE_APPLICATION_CREDENTIALS"}
for _, v := envs {

}
```
