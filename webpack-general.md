# WEBPACK

## Add NPM support to webpack
```
{
    resolve: { modulesDirectories: ['public/js', 'node_modules'] }
}
```

## Debug In Chrome Dev Tools
https://medium.com/webpack/webpack-bits-learn-and-debug-webpack-with-chrome-dev-tools-da1c5b19554#.runij6tay

## CLI
### export statistics on build
`webpack --profile --json > stats.json`

## Config Outputs
### output filename
only affects output bundles not require.ensures. Must NOT be an absolute path
`output: { filename: '[name].[chunkhash].js' }`

### output path MUST be an absolute path
`output: { path: path.join(__dirname, 'app/dist/') }`

### public path for s3 static site use
`output: { path: path.join(__dirname, 'app/dist/') }`

## REQUIRES
### Require file from another chunk / module with .ensure
```
require.ensure([
  '../services/media/mymedia.media.svc'
], (obj) => {
  let MyMediaService = obj;
});
```

## CONFIG
### CONTEXT
Context must be an absolute path. Entry should be string names

### Minimized bundle size
`devtool: 'cheap-module-source-map'`

## PLUGINS
### Define a Plugin
https://webpack.github.io/docs/list-of-plugins.html#defineplugin

### Hot module replacement plugin
```
if (process.env.NODE_ENV === "development" ) {
     plugins.push(new webpack.HotModuleReplacementPlugin());
}
```

### Show Timestamp
```
  plugins: [
    function timestamp() {
      this.plugin('watch-run', function(watching, callback) {
        console.log('Begin compile at ' + new Date());
        callback();
      });
    },
  ],
```

### Ignore Plugin if environment is test
```
const isTest = process.env.NODE_ENV === 'test'
plugins: [
    isTest ? undefined : new webpack.optimize.CommonsChunkPlugin({ name: 'vendor', })
].filter(p => !!p)
```

### Rewrite process.env to production in code
```
    new webpack.DefinePlugin({
             'process.env.NODE_ENV': '"production"'
    })
```


## ESLINT
### eslint loader has to come after babel-loader
webpack enacts loaders from bottom to top, right to left
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

### preLoaders
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

### options can be passed directly to eslint such as:
```
module.exports = {
  eslint: {
    configFile: 'path/.eslintrc',
    failOnError: true
  }
}
```

