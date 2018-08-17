# JAVASCRIPT MUTATIONS
(https://stackoverflow.com/questions/7574054/javascript-how-to-pass-object-by-value)

Remember Arrays and nested objects are passed by reference!

## OK
does not allow mutate
```
var o = {};
(function(x){
    var obj = Object.create( x );
    obj.foo = 'foo';
    obj.bar = 'bar';
})(o);

alert( o.foo ); // undefined
```

## BAD
mutates
```
var o = {
    baz: []
};
(function(x){
    var obj = Object.create( x );

    obj.baz.push( 'new value' );

})(o);

alert( o.baz[0] );  // 'new_value'
```

## OK
```
var o = {
    baz: []
};
(function(x){
    var obj = Object.create( x );

    obj.baz = [];
    obj.baz.push( 'new value' );

})(o);

alert( o.baz[0] );  // undefined
```
