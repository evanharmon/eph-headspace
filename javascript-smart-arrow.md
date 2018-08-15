# JAVASCRIPT SMART ARROW

## Always Anonymous.
Binds the `this` value

## Basic Syntax
ES5: `const multiply = function(x, y) { return x * y; };`
ES6: `const multiply = (x,y) => { return x * y; };`

## Curly Brackets are not required if only one expression is present
`const multiply = (x,y) => x * y;`

## No Parameters, Parantheses required
```
const docLog = () => { console.log(document); };
docLog();
```

## Single Parameter, Parantheses are optional
ES5
`const splitter = function(phrase) { return phrase.split(' '); };`
`const splitter = phrase => phrase.split(" ");`

## Return Object Literal
ES5
`const setNameIds = function(id, name) { return { id: id, name: name }; };`
ES6
`const setNameIds = (id, name) => ({ id, name });`

## Expression body is always implicitly returned
ES5: `const squares = [1,2,3].map(function(x) { return x * x });`
ES6: `const squares = [1,2,3].map(x => x * x);`
