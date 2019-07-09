# GOLANG HTTP

## Summary

Notes on working with HTTP in golang

## Mock HTTP Request

package is `net/http/httptest`

```golang
ts := httptest.NewServer(http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
    w.Write([]byte(`desired response here`))
}))
defer ts.Close()
apiURL = ts.URL

myfunction(apiURL)
```
