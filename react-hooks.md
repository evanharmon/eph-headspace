# REACT HOOKS

## Summary

Notes on using react hooks

## Resources

[HOOKS Blog](https://www.robinwieruch.de/react-hooks-fetch-data/)
[API](https://reactjs.org/docs/hooks-reference.html#usecontext)
[useContext between files](https://upmostly.com/tutorials/how-to-use-the-usecontext-hook-in-react/)
[Loading Context example](https://medium.com/digio-australia/using-the-react-usecontext-hook-9f55461c4eae)
[RoadMap](https://reactjs.org/blog/2018/11/27/react-16-roadmap.html)

## useAnimationFrame Custom Hook

[Sandbox](https://codesandbox.io/s/ojxl32jm4z)

## Context

[Avoid Passing Callbacks Down](https://reactjs.org/docs/hooks-faq.html#how-to-avoid-passing-callbacks-down)

From the React Team:

```
If you use context to pass down the state too, use two different context types —
the dispatch context never changes, so components that read it don’t need to
rerender unless they also need the application state.
```

## Fetch Data With React Hooks

[Robin Weiruch Blog](https://www.robinwieruch.de/react-hooks-fetch-data/)
[Audisho.Sada Medium Example](https://medium.com/@audisho.sada/using-react-hooks-to-asynchronously-make-api-requests-1fdf52f797ce)

In the future, `react-cache` and `suspense` will be used for data fetching

## Common Errors

#### UseCustom Hook Undefined

Set initial state `const [collection, setCollection] = useState({})` in the
custom hook

## Testing Hooks

[react-hooks-testing-library](https://react-hooks-testing-library.com/usage/advanced-hooks)

## isMounted Technique

only needs to be used AFTER an `await` statement checking `if (isMounted)` or
in the `catch` block of a try catch like `if (isMounted) console.log(error)`
