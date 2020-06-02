# JAVASCRIPT FIRST CLASS FUNCTIONS
(https://www.gitbook.com/book/drboolean/mostly-adequate-guide)

## JS Functions are First-Class
this line
```
return ajaxCall(function(json) {
  return callback(json);
});
```

is the same as this line
```
return ajaxCall(callback);
```

so refactor getServerStuff
```
var getServerStuff = function(callback) {
  return ajaxCall(callback);
};
```

...which is equivalent to this
`var getServerStuff = ajaxCall; // <-- look mum, no ()'s`

## Avoid Having to re-write functions
```
httpGet('/post/2', function(json) {
  return renderPost(json);
});
```

```
httpGet('/post/2', function(json, err) {
  return renderPost(json, err);
});
```
Had we written it as a first class function, much less would need to change:
renderPost is called from within httpGet with however many arguments it wants
`httpGet('/post/2', renderPost);`

## Beware of This
Having been bound to itself, the Db is free to access its prototypical garbage
code. I avoid using this like a dirty nappy. There's really no need when
writing functional code. However, when interfacing with other libraries, you'll
have to acquiesce to the mad world around us

`var fs = require('fs');`

scary
`fs.readFile('freaky_friday.txt', Db.save);`

less so
`fs.readFile('freaky_friday.txt', Db.save.bind(Db));`

## Avoid Side Effects
A side effect is a change of system state or observable interaction with the
outside world that occurs during the calculation of a result

- changing the file system
- inserting a record into a database
- making an http call
- mutations
- printing to the screen / logging
- obtaining user input
- querying the DOM
- accessing system state
