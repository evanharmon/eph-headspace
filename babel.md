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
