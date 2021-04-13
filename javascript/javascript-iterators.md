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

Requires the use of iterables

```javascript
for await (variable of iterable) {
  statement
}
```

## Await an Array of Promises

```
async function myApiCall(time) {
  await new Promise(resolve => setTimeout(resolve, time));
}
const times = [5000, 3000, 1000];
async function run(arr) {
  for (let time of arr) {
  console.log("starting: ", time);
  await myApiCall(time);
  console.log("completed: ", time);
  }
}
run(times);
```

## Await .map

- [article](https://flaviocopes.com/javascript-async-await-array-map/)

```javascript
const getData = async (list = []) => {
  return new Promise.all(
    list.map(async (i) => {
      await someAsyncCall()
    })
  )
}
```
