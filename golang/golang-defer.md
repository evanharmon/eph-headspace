# GOLANG DEFER
defer function is called even on a panic and the function terminates
unexpectedly

## Check Defer Error
```golang
f, err := os.Open(fname)
if err != nil {
  return err
}
defer func(file *os.File) {
  if err := file.Close(); err != nil {
    log.Fatal(err)
  }
}(f)
```
