# NODE NETWORKING

## Build Up query
```
const redirectUrl = URL.format({
   pathname: hostname + "/route",
   query: { email: emailVar }
};
```

## Curl Request
```
const { request } = require("http");

const options = {
  host: 'www.google.com',
  port: 80,
  path: '/upload',
  method: 'POST'
};

const req = request(options, res => {
  res.setEncoding('utf8');
  res.on('data', chunk => {
    console.log('BODY: ' + chunk);
  });
});

req.on('error', e => {
  console.log('problem with request: ' + e.message);
});

// write data to request body
req.write('data\n');
req.end();
```
