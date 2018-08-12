# NODE EXPRESS REACT EXAMPLE
```
const path = require('path');
const Express = require('express');

const app = new Express();
const port = 3000;

app.use(Express.static(path.resolve(__dirname, 'dist')));
app.use('/', (req, res) => {
  res.sendFile(path.resolve(__dirname, 'dist', 'index.html'));
});

app.listen(port, (error) => {
  // eslint-disable-line no-console
  // eslint-disable-line comma-dangle
  if (error) {
    console.error(error);
  } else {
    console.info(
      '🌎 Listening on port %s.',
      port
    );
  }
  // eslint-enable-line no-console
  // eslint-enable-line comma-dangle
});
```
