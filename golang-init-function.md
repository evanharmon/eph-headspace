# GOLANG INIT FUNCTION

## Summary
Notes on using the init function in golang

## Resources
[Medium](https://medium.com/golangspec/init-functions-in-go-eac191b3860a)

## Example
```
var AppConfig interface{}

func LoadConfig(filename string) (cfg interface{}, err Error) {
	configFile, err := os.Open(filename)
	defer file.Close()
	if err != nil {
		return ErrFileIo
	}
	AppConfig = json.NewDecoder(configFile).Decode(&config)
}

func init() {
  if let err = LoadConfig("myconfigfile.json"); err != nil {
    panic(err)
  }
}
```
