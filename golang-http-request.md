# GOLANG HTTP REQUEST

## Get a form field

```golang
r.ParseForm()
id := r.Form["id"]
```

## Check Response Codes

avoid `suspect or` by using two separate ifs

```golang
if resp.StatusCode < 200 {
  return nil, fmt.Errorf("HTTP Response error status: %d\n", resp.StatusCode)
}

if resp.StatusCode > 201 {
  return nil, fmt.Errorf("HTTP Response error status: %d\n", resp.StatusCode)
}
```

## Example

```golang
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

## Recalculate Content Length

```golang
b, err := io.Copy(ioutil.Discard, req.Body)
```
