# REACT CONTEXT

## Summary

Notes on using react context

## Resources

[Docs useContext](https://reactjs.org/docs/hooks-reference.html#usecontext)

## Export useContext

```javascript
import React, { useContext } from "react";

const MyStateContext = React.createContext();

function useMyState() {
  const context = useContext(MyStateContext);
  return context;
}

export { useMyState };
```

## Import Exported useContext

`createContext` call returns an object

```javascript
function MyComponent() {
  const state = useMyState();
}
```
