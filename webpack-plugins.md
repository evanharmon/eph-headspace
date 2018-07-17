# Define a Plugin
https://webpack.github.io/docs/list-of-plugins.html#defineplugin

# Hot module replacement plugin
```
if (process.env.NODE_ENV === "development" ) {
     plugins.push(new webpack.HotModuleReplacementPlugin());
}
```

# Show Timestamp
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

# Ignore Plugin if environment is test
```
const isTest = process.env.NODE_ENV === 'test'
plugins: [
    isTest ? undefined : new webpack.optimize.CommonsChunkPlugin({ name: 'vendor', })
].filter(p => !!p)
```

# Rewrite process.env to production in code
```
    new webpack.DefinePlugin({
             'process.env.NODE_ENV': '"production"'
    })
```
