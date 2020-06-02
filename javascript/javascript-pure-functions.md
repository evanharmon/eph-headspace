# JAVASCRIPT PURE FUNCTIONS

## Impure
```
var signUp = function(attrs) {
  var user = saveUser(attrs);
  welcomeUser(user);
};
```

```
var saveUser = function(attrs) {
    var user = Db.save(attrs);
    ...
};
```

```
var welcomeUser = function(user) {
    Email(user, ...);
    ...
};
```

## Pure
```
var signUp = function(Db, Email, attrs) {
  return function() {
    var user = saveUser(Db, attrs);
    welcomeUser(Email, user);
  };
};
```

```
var saveUser = function(Db, attrs) {
    ...
};
```

```
var welcomeUser = function(Email, user) {
    ...
};
```
