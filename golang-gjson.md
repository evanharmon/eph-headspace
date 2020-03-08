# GOLANG JSON

## Summary

Notes on using the tidwall/gjson package

## Resources

- [Tidwall/gjson](https://github.com/tidwall/gjson)
- [GJSON Playground](https://gjson.dev/)

## Parse JSON

```golang
title := gjson.Get(*msg.Body, "data.title")
fmt.Printf(title.String())
```
