# JAVASCRIPT RECIPES

## Summary

Common short recipes for javascript tasks

## Resources

### Parse Email Address

#### Get Domain Name

be safe and only grab last '@'

```javascript
const email = 'user@example.com'
const idx = email.lastIndexOf('@')
const domain = email.substring(`${idx + 1}`)
```
