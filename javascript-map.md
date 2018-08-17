# JAVASCRIPT MAP
Must use return or map will not be returned!

## Good way to grab nested property values of an array of objects
example: need Order.Customer.Id array
`Orders.map(o => o.Customer.Id);`

## Return early and break map process
not possible to return early

## In Browser, download scripts in parallel and execute them in order
```
function inject(src) {
  var script = document.createElement('script');
  script.src = src;
  // Load dynamically injected scripts async, execute them sync
  script.async = false;
  document.body.appendChild(script);
}

['thirdparty', 'shared', 'app'].map(getModuleSrc).forEach(inject);
```
