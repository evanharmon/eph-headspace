# NODE REQUESTJS

## POST Form Requests
```
request
  .post('http://service.com/upload', { form: { key: 'value'} })
request
  .post({ url:'http://service.com/upload', form: { key: 'value' } },
    (err, httpResponse, body) => { /* ... */ }
  );
```

## Send Cookie With a Request
may have to look in req.headers.cookie if no cookie-parsing module is being used
referencing `connect.sid` can be difficult
```
request({
  url: 'http://localhost:3000/users/api',
  headers: { Cookie: somedataHere }
  }, (error, response, body) => {
    res.render('../views/admin');
});
```
