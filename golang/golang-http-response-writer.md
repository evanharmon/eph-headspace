# GOLANG HTTP RESPONSE WRITER

## Send response with a body
```
func sayIDAuthor(w http.ResponseWriter, r *http.Request) {
    r.ParseForm()
    fmt.Println(r.Form) // print form information in server side
    fmt.Println("path", r.URL.Path)
    fmt.Println("scheme", r.URL.Scheme)
    fmt.Println(r.Form["url_long"])
    for k, v := range r.Form {
        fmt.Println("key:", k)
        fmt.Println("val:", strings.Join(v, ""))
    }

    fmt.Fprintf(w, "Hello astaxie!") // send data to client side
}
```
