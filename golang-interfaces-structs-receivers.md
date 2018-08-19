# GOLANG INTERFACES STRUCTS RECEIVERS

## Example from GoKit addsvc / profilesvc

#### service.go
Interface includes methods to be attached to empty struct
Empty struct is declared, NewService method returns the struct with attached
interface with methods to be used like PostNote
```
package storesvc

import (
    "context"
    "fmt"
)

type Service interface {
    PostNote(ctx context.Context, n Note) (Note, error)
}

type Note struct {
    ID     string `json:"id,omitempty"`
    Rev    string `json:"_rev,omitempty"`
    Author string `json:"author,omitempty"`
    Title  string `json:"title"`
    Text   string `json:"text"`
}

type noteService struct{}

func NewService() Service {
    return noteService{}
}

func (s noteService) PostNote(ctx context.Context, n Note) (Note, error) {
    fmt.Printf("svc PostNote \n")
    n = Note{
        ID:     "1234",
        Rev:    "4321",
        Author: "Evan Harmon",
        Title:  "Title",
        Text:   "text",
    }
    return n, nil
}
```

# main.go
NewService call returns empty struct with the attached methods from storesvc
like PostNote
```
package main

import ("github.com/harmonsoftwaresolutions/hss-notes-store/storesvc”)

func main() {
    var s storesvc.Service
    {
        s = storesvc.NewService()
        // s = storesvc.LoggingMiddleware(logger)(s)
    }
}
```
