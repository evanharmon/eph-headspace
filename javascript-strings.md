# JAVASCRIPT STRINGS

## Summary

Notes on working with strings in Javascript

## Resources

## Get decimal value of a string

`"↵".charCodeAt(0)`

## Get hex of string from decimal

`(8629).toString(16)`

## Pad a number with 0's

`const orderIDPadded = orderID.padStart(12, '0');`

## Get Size In Bytes

use node.js. Much much easier

```javascript
function getBinarySize(string) {
  return Buffer.byteLength(string, "utf8");
}
getBinarySize("ta-daaaaa");
```

## Escape Double Quotations

```javascript
`email = \\${JSON.stringify(email)}\\`;
```

prints `"email = \"eharmon@gmail.com"\"`

## Reverse A String

```javascript
const reverse = str =>
  Array.from(str)
    .reverse()
    .join("");
```
