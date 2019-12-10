# REACT DEBUGGING

## Summary

Notes on debugging React

## Resources

- [Github Why Did You Render](https://github.com/welldone-software/why-did-you-render)

## Debugging Renders

### Why Did You Render

example use in `src/index.js`

```javascript
if (process.env.NODE_ENV !== 'production') {
  const whyDidYouRender = require('@welldone-software/why-did-you-render')
  whyDidYouRender(React)
}
```

components must be tagged

```javascript
function MyComponent() {}
MyComponent.whyDidYouRender = true
```
