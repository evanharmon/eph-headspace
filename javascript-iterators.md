# JAVASCRIPT ITERATORS

## Summary

Notes on iterating / looping in javascript

## Resources

- [for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
- [for await of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for-await...of)
- [Blog For Loop Await](https://lavrton.com/javascript-loops-how-to-handle-async-await-6252dd3c795/)

## For Of On Arrays

```javascript
const array1 = ['a', 'b', 'c']

for (const element of array1) {
  console.log(element)
}
```

## For In vs For Of

The for...in statement iterates over the enumerable properties of an object, in an arbitrary order.

The for...of statement iterates over values that the iterable object defines to be iterated over.

## For Of With Await

```javascript
for await (variable of iterable) {
  statement
}
```
