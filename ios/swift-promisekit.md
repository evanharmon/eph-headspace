# SWIFT PROMISEKIT

## Summary

Notes on using the promisekit pod in swift

## Resources

- [Github Repo](https://github.com/mxcl/PromiseKit)
- [Getting Started](https://github.com/mxcl/PromiseKit/blob/master/Documentation/GettingStarted.md)
- [PromiseKit from a javascript perspective](https://chariotsolutions.com/blog/post/swift-4-and-promisekit/)

### Helper Functions

#### Convert Promise Return Type

```swift
.asVoid()
```

### Troubleshooting

#### Cannot convert value of type `Promise<>` to closure result type `Guarantee<>`

make sure a .catch isn't being returned to a function returning a promise!
