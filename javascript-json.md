# JAVASCRIPT JSON

## Summary

Notes on working with JSON in lovely javascript

## Resources

[SO Serialization](https://stackoverflow.com/questions/41847581/what-is-the-difference-between-object-assign-and-json-parsejson-stringifyobj)

## JSON.stringify()

Performs a deep copy

## Pretty Print JSON

```javascript
console.log("newArr %s", JSON.stringify(newArr, null, "\t"));
```

## JSON.stringify Circular Fix

[SO](https://stackoverflow.com/questions/11616630/how-can-i-print-a-circular-structure-in-a-json-like-format<Paste>)

```javascript
const getCircularReplacer = () => {
  const seen = new WeakSet();
  return (key, value) => {
    if (typeof value === "object" && value !== null) {
      if (seen.has(value)) {
        return;
      }
      seen.add(value);
    }
    return value;
  };
};

JSON.stringify(circularReference, getCircularReplacer());
```
