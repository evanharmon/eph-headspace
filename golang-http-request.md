# GOLANG HTTP REQUEST

## Get a form field
```
r.ParseForm()
id := r.Form["id"]
```

## Example
```
package main

import (
"fmt"
"strings"
"net/http"
"io/ioutil"
)

func main() {

url := "https://localhost:4984/sync_gateway/_changes"

payload := strings.NewReader("{\n\t\"include_docs\": false,\n\t\"filter\": \"sync_gateway/bychannel\",\n\t\"channels\": \"example\",\n\t\"limit\": 50\n}")

req, _ := http.NewRequest("POST", url, payload)

req.Header.Add("content-type", "application/json")
req.Header.Add("cache-control", "no-cache")

res, _ := http.DefaultClient.Do(req)

defer res.Body.Close()
body, _ := ioutil.ReadAll(res.Body)

fmt.Println(res)
fmt.Println(string(body))
}
```
