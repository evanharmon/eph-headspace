# JAVASCRIPT HELPERS

## Summary
Common helper functions in javascript

## Internet Addresses

### Defang IP Address

```javascript
Array.from(address).map(i => i === '.' ? '[.]' : i).join('')
```
