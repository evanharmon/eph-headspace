# JAVASCRIPT EXPORTS

## Summary

Notes on using es6 exports with Node

## Export Individual Functions With A Default

```javascript
export { objectLessAttributes as default, myOtherFunction }
```

## Re-Export Default From File

for example in an `index.js` file inside a folder:
`src/MyComponent/index.js`

```javascript
export { default as JS, myotherFunction } from './JS'
```
