# GOLANG INTERFACES
Used to declare behavior. Never includes actual implementation for the type

## Interface Values
two-word data structures
first-word: pointer to iTable
second-word: pointer to stored value

## iTable
contains:
type of value
list of methods associated with value

## Naming Conventions
If interface only has a single method, name the interface ending with 'er'
```golang
type Worker interface {
  Search()
}
```
