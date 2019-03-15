# JAVASCRIPT SETS

## Distinct Array

`const j = [...new Set([1, 2, 3, 3])]`

> > [1, 2, 3]

## Create Set From Array Of Filenames

```javascript
const filenames = readdirSync(./src/graphql/)
const map = filenames.map(f => {
  const match = new RegExp(/^(.+?\..+?)\b/, "g").exec(f);
  return `${match[1]}`;
});
const set = [...new Set(map)];
```
