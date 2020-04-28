# CHROME DEV TOOLS

## Summary

Notes on using chrome dev tools

## Get HTML Contents Of iFrame

Dev tools select, elements, expand iFrame element, highlight html element and
copy element

## Debug NodeJS Webpack Inside Chrome Dev Tools

```
node --inspect-brk ./node_modules/.bin/webpack --config webpack.prod.config.js
```

## Find Large Images / Responses

In search bar of Network
`larger-than:20K`

## Launch Debugger And Pause On Redirects

```javscript
window.addEventListener("beforeunload", function() { debugger; }, false)
```

or

```javascript
window.beforeunload = () => {
  debugger
}
```
