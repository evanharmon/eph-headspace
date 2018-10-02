# JAVASCRIPT

# Check for non-empty Strings
`const check = password.length > 0;`

# Remove Whitespace / Line Breaks
`const cleanString = "\nSome data\n".replace(/(\r\n|\n|\r|\t)/g, "").trim();`

# Remove Spaces
```javascript
"test phrase".replace(/\s/g, '');
```

# Compare property value to array of values indexOf
## avoids long if/ternary statements
`['Open', 'Closed'].indexOf(varName) !== -1`

# Perform same action for multiple switch cases
## works by omitting break on case
```
switch(TARGET) {
  case 'test':
  case 'test:tdd':
      config = merge(common, {});
      break;
}
```

# Front-end Change readable-stream Response From Server to Object
(https://developer.mozilla.org/en-US/docs/Web/API/Response)
`res.body.json()`

# Interpolate Strings
`http://${url}`

# String replaceAll
`target.split(search).join(replacement)`

# Remove Leading 0's
`parseInt("010", 10)`

# Contains
`use indexOf()`

# Pretty Print JSON
`console.log('newArr %s', JSON.stringify(newArr, null, '\t'));`
