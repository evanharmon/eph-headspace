# BABEL

## Summary

Notes on using babel with nodejs

## Error Expected Version 7

Error Requires Babel "^7.0.0-0", but was loaded with "6.26.3"
example error where current eslint requires babel-core v6. Have to install the
[bridge](https://github.com/babel/babel-bridge)

```console
npm i -D babel-core@^7.0.0-bridge.0
```

## Error runtimeGenerator Not Defined

Check babel config, especially '@babel/preset-env'

good config
[GH Issue](https://github.com/facebook/jest/issues/7579)

```javascript
// babel.config.js
module.exports = {
  presets: [["@babel/preset-env", { targets: { node: "current" } }]]
};
```
