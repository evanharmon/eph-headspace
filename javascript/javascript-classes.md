# JAVASCRIPT CLASSES

## Resources

- [MDN Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
- [Class Bodies Executed in Strict Mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)

## Classes and binding have a memory cost

## Auto Binding Methods

put inside constructor

```javascript
this.method = this.method.bind(this)
```

## When to use Classes

Need access to 'this', then declare methods in class, otherwise use regular
components

## Static Methods

useful for utility functions

- can be called without instanciating the class
- CANNOT be called through a class instance

## Static Properties

useful for caches, fixed-configuration, data you don't need replicated across instances
