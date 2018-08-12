# NODE FETCH
[repo](https://github.com/bitinn/node-fetch)

## Response object
```
res.body
res.status
res.statusText
```

## Example
```
const params = new URLSearchParams();
const res = await fetch('http://httpbin.org/post', {
   method: 'POST',
   body: params,
   }
);
console.log(res.status);
```
