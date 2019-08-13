# REACT COMMON ERRORS

## Summary

Notes on common errors in React

## Resources

[RWeiruch UnMounted Component Set State Warning](https://www.robinwieruch.de/react-warning-cant-call-setstate-on-an-unmounted-component/)

## React must be in scope

make sure your import is capital R

```javascript
import React from "react";
```

## Invariant

Bad

```javascript
export default React.createClass({});
```

Good

```javascript
const App = React.createClass({});
export default App;
```

## Commenting in JSX

```javascript
{
  /* A JSX comment */
}
```

## Objects are not valid as a React child

Returning an object where React is expecting a string. Look for an empty object
inside a jsx comment, or a return statement mismatch between () and {}
