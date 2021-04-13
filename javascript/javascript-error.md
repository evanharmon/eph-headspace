# JAVASCRIPT ERROR

## Summary

General notes on javascript error type

## Resources

- [MDN ERROR TYPE](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)

## Custom Error Class

```javascript
class CustomError extends Error {
  constructor(...args) {
    super(...args)
    if (Error.captureStackTrace) {
      Error.captureStackTrace(this, CustomError)
    }
    this.name = 'Our Custom Error'
  }
}

try {
  throw new CustomError('Something went wrong')
} catch (err) {
  console.error(err.stack)
}
```
