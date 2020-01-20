# JAVASCRIPT

## Summary

General notes on javascript

## Resources

- [Eloquent Javascript](https://eloquentjavascript.net/)
- [You Don't Know Javascript](https://github.com/getify/You-Dont-Know-JS)
- [Javascript Snippets 30 Seconds of code](https://github.com/30-seconds/30-seconds-of-code)

## Check for non-empty Strings

```javascript
const check = password.length > 0
```

## Remove Whitespace / Line Breaks

```javascript
const cleanString = 'n'.replace(/(\r\n|\n|\r|\t)/g, '').trim()
```

## Remove Spaces

```javascript
'test phrase'.replace(/\s/g, '')
```

## Compare property value to array of values indexOf

avoids long if/ternary statements

```javascript
;['Open', 'Closed'].indexOf(varName) !== -1
```

## Perform same action for multiple switch cases

works by omitting break on case

```javascript
switch (TARGET) {
  case 'test':
  case 'test:tdd':
    config = merge(common, {})
    break
}
```

## Front-end Change readable-stream Response From Server to Object

[MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response)

```javascript
res.body.json()
```

## Interpolate Strings

```javascript
http://${url}
```

## String replaceAll

```javascript
target.split(search).join(replacement)
```

## Remove Leading 0's

```javascript
target.split(search).join(replacement)
```

parseInt("010", 10)

## Contains

use `indexOf()`
