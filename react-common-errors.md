# REACT COMMON ERRORS

## React must be in scope
make sure your import is capital R
`import React from "react";`

## Invariant
Bad
`export default React.createClass({})`

Good
```
const App = React.createClass({})
export default App;
```

## Commenting in JSX
`{/* A JSX comment */}`

## Objects are not valid as a React child
Returning an object where React is expecting a string. Look for an empty object
inside a jsx comment, or a return statement mismatch between () and {}
