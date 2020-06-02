# JAVASCRIPT SETS

## Summary

Notes on working with Sets in javascript

## Distinct Array

`const j = [...new Set([1, 2, 3, 3])]`

> > [1, 2, 3]

## Distinct Array Of Objects

[dev.to](https://dev.to/vuevixens/removing-duplicates-in-an-array-of-objects-in-js-with-sets-3fep)

## Create Set From Array Of Filenames

```javascript
const filenames = readdirSync(./src/graphql/)
const map = filenames.map(f => {
  const match = new RegExp(/^(.+?\..+?)\b/, "g").exec(f);
  return `${match[1]}`;
});
const set = [...new Set(map)];
```
