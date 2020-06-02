# GOLANG HEALTHCHECK

## Summary

Simple health check with test for Golang

## Resources

[Matt Silverlock](https://blog.questionable.services/article/testing-http-handlers-go/)

## Example Go

```golang
func HealthCheckHandler(w http.ResponseWriter, r *http.Request) {
    w.WriteHeader(http.StatusOK)
    w.Header().Set("Content-Type", "application/json")
    io.WriteString(w, `{"alive": true}`)
}
http.HandleFunc("/ping", HealthCheckHandler)
```

## Example Test

```golang
package main

import (
    "net/http"
    "net/http/httptest"
    "testing"
)

func TestHealthCheckHandler(t *testing.T) {
    req, err := http.NewRequest("GET", "/ping", nil)
    if err != nil {
    •   t.Fatal(err)
    }

    rr := httptest.NewRecorder()
    handler := http.HandlerFunc(HealthCheckHandler)
    handler.ServeHTTP(rr, req)

    if status := rr.Code; status != http.StatusOK {
    •   t.Errorf("handler returned wrong status code: got %v want %v", status, http.StatusOK)
    }

    expected := `{"alive": true}`
    if rr.Body.String() != expected {
    •   t.Errorf("handler returned unexpected body: got %v want %v", rr.Body.String(), expected)
    }
}
```
