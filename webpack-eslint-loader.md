# eslint loader has to come after babel-loader
## webpack enacts loaders from bottom to top, right to left
```
module.exports = {
  // ...
  module: {
    loaders: [
      {test: /\.js?/, loaders: [ "babel-loader", "eslint-loader" ], exclude: /node_modules/},
    ]
  }
  // ...
}
```

# preLoaders
To be safe, you can use preLoaders section to check source files, not modified
by other loaders (like babel-loader)
```
module.exports = {
  // ...
  module: {
    preLoaders: [
      {test: /\.js?/, loader: "eslint-loader", exclude: /node_modules/}
    ]
  }
  // ...
}
```

# options can be passed directly to eslint such as:
```
module.exports = {
  eslint: {
    configFile: 'path/.eslintrc',
    failOnError: true
  }
}
```
