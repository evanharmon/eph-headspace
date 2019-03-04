# ESLINT DISABLE

## Summary

Notes on disabling eslint

## Resources

[Eslint Configuration](https://eslint.org/docs/user-guide/configuring)

## Single Line Disable

```js
// eslint-disable-next-line global-require
```

## Disable Multiple Lines

```js
/* eslint-disable */

alert("foo");

/* eslint-enable */
```

## Global Disable

```js
/* eslint global-require: "warn" */
```
