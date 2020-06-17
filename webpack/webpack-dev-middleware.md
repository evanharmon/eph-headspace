# Use HtmlWebpackPlugin
## in a devServer.js file
```
import path from 'path';
import webpack from 'webpack';
import webpackDevMiddleware from 'webpack-dev-middleware';
import config from './webpack.config.babel';
import Express from 'express';

const app = new Express();
const port = 3000;

const compiler = webpack(config);
app.use(webpackDevMiddleware(compiler, {
  noInfo: true,
  publicPath: config.output.publicPath,
}));

// app.get('/', (req, res) => {
  // res.sendFile(path.join(__dirname, 'dist', 'index.html'));
// });

app.use('*', (req, res, next) => {
  const filename = path.join(compiler.outputPath, 'index.html');
  compiler.outputFileSystem.readFile(filename, (err, result) => {
    if (err) next(err);

    res.set('content-type', 'text/html');
    res.send(result);
    res.end();
  });
});

app.listen(port, (error) => {
  /* eslint-disable no-console */
  if (error) {
    console.error(error);
  } else {
    console.info(
      '🌎 Listening on port %s. Open up http://localhost:%s/ in your browser.',
      port,
      port,
    );
  }
  /* eslint-enable no-console */
});
```
