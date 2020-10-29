# GOLANG INTERFACES

## Summary

Used to declare behavior. Never includes actual implementation for the type

## Resources

- [Convert Types To Interface Via Copy](https://golang.org/doc/faq#convert_slice_of_interface)

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
