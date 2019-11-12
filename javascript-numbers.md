# JAVASCRIPT NUMBERS

## Summary

Notes on working with javascript numbers

## Resources

## Check For 32bit Overflow

[SO](https://stackoverflow.com/questions/47600096/what-is-32-bit-integer-in-javascript)

```javascript
if (myInt > Math.pow(2, 31) - 1) {
  return 0;
}
```
