# JAVASCRIPT DESTRUCTURINGG

## Summary

Notes on javascript es6 and on destructuring

## Resources

[Medium Article](https://medium.com/dailyjs/named-and-optional-arguments-in-javascript-using-es6-destructuring-292a683d5b4e)

## Destructure Assignment Limited to Specific Properties in an Object

(https://gist.github.com/mikaelbr/9900818)

## Rename Destructured assignment parameters

````javascript
myFunc = function({ x: newX, y: newY, z: newZ }) {
  console.log(newX, newY, newZ);
};

myFunc({ x: 10, y: 20, z: 30 }); //10 20 30```
````
