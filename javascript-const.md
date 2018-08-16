# JAVASCRIPT CONST

[FROM MDN]
(https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

## Definition
Constants are block-scoped, much like variables defined using the let statement.
The value of a constant cannot change through re-assignment, and it can't be
redeclared

## Examples from MDN
Constants can be declared with uppercase or lowercase, but a common convention
is to use all-uppercase letters

define MY_FAV as a constant and give it the value 7
`const MY_FAV = 7;`

this will throw an error
`MY_FAV = 20;`

will print 7
`console.log("my favorite number is: " + MY_FAV);`

trying to redeclare a constant throws an error
`const MY_FAV = 20;`

the name MY_FAV is reserved for constant above, so this will also fail
`var MY_FAV = 20;`

this throws an error also
`let MY_FAV = 20;`

it's important to note the nature of block scoping
```
if (MY_FAV === 7) {
    // this is fine and creates a block scoped MY_FAV variable
    // (works equally well with let to declare a block scoped non const variable)
    const MY_FAV = 20;

    // MY_FAV is now 20
    console.log("my favorite number is " + MY_FAV);

    // this gets hoisted into the global context and throws an error
    var MY_FAV = 20;
}
```

MY_FAV is still 7
`console.log("my favorite number is " + MY_FAV);`

throws an error, missing initializer in const declaration
`const FOO;`

const also works on objects
`const MY_OBJECT = {"key": "value"};`

Attempting to overwrite the object throws an error
`MY_OBJECT = {"OTHER_KEY": "value"};`

However, object keys are not protected,
so the following statement is executed without problem
`MY_OBJECT.key = "otherValue"; // Use Object.freeze() to make object immutable`

The same applies to arrays
`const MY_ARRAY = [];`
It's possible to push items into the array
`MY_ARRAY.push("A"); // ["A"]`
However, assigning a new array to the variable throws an error
`MY_ARRAY = ["B"]`
