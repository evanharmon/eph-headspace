# JAVASCRIPT OBJECTS

## Dynamically Add properties to an object
```
const v = {}
v.sortByHeaderProp = prop => {
  v.sortedStates = {}; // clear
  v.sortedStates[prop] = v.sortedStates[prop] === 'asc' ? 'desc' : 'asc';
  v.myCustomerBills = _.orderBy(v.myCustomerBills, prop, v.sortedStates[prop]);
};
const acc = {};
acc[OrderNo] = '13455';
```

## Check if an object has any properties
`Object.keys(obj).length === 0`

## Check if an Object Has a Specific Property
does not traverse prototype chain
```
let o = {};
o.hasOwnProperty()
```

## Build Nested Object
```
const nest = (obj, keys, v) => {
    if (keys.length === 1) {
      obj[keys[0]] = v;
    } else {
      var key = keys.shift();
      obj[key] = nest(typeof obj[key] === 'undefined' ? {} : obj[key], keys, v);
    }

    return obj;
};
```

## Example
```
const dog = {bark: {sound: 'bark!'}};
nest(dog, ['bark', 'loudness'], 66);
nest(dog, ['woff', 'sound'], 'woff!');
console.log(dog); // {bark: {loudness: 66, sound: "bark!"}, woff: {sound: "woff!"}}
```

## Short-hand Object Properties
Object Property Values in a shorthand way
```
let firstName = "john";
let lastName = "smith";
let person = {firstName, lastName};
```

## Computed Property
will evaluate, do string concatenation, etc
```
let color = "red";
let speed = 10;
let drive = "go";

const car = {
     color,
     speed,
     [drive]: function() { console.log("vroom"); }
};
```
