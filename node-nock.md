# NODE NOCK
(https://github.com/node-nock/nock)

## Send Response Code and Data
```
nock('http://myapp.iriscouch.com')
  .get('/users/1')
  .reply(200, {
    _id: '123ABC',
    _rev: '946B7D1C',
    username: 'pgte',
    email: 'pedro.teixeira@gmail.com'
  });
```

## Example with Fetch
```
  const apiUrl = 'http://localhost:3000';
  nock(apiUrl)
    .get('/group/user')
    .reply(400);

  const fetchUrl = 'http://localhost:3000/group/user';
  const res = await fetch(fetchUrl);
```
