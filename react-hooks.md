# REACT HOOKS

## Summary

Notes on using react hooks

## Resources

- [HOOKS Blog](https://www.robinwieruch.de/react-hooks-fetch-data/)
- [API](https://reactjs.org/docs/hooks-reference.html#usecontext)
- [useContext between files](https://upmostly.com/tutorials/how-to-use-the-usecontext-hook-in-react/)
- [Loading Context example](https://medium.com/digio-australia/using-the-react-usecontext-hook-9f55461c4eae)
- [RoadMap](https://reactjs.org/blog/2018/11/27/react-16-roadmap.html)
- [Docs UseLayout](https://reactjs.org/docs/hooks-reference.html#uselayouteffect)
- [useRef Hook Medium Blog](https://medium.com/@rossbulat/react-using-refs-with-the-useref-hook-884ed25b5c29)
- [useRef Docs](https://reactjs.org/docs/hooks-reference.html#useref)
- [Hooks Cheat Sheet](https://blog.logrocket.com/react-hooks-cheat-sheet-unlock-solutions-to-common-problems-af4caf699e70/)
- [useState or useReducer](https://kentcdodds.com/blog/should-i-usestate-or-usereducer)

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

### Example

```javascript
test('should use custom step when incrementing', () => {
  const wrapper = ({ children }) => (
    <CounterStepProvider step={2}>{children}</CounterStepProvider>
  )
  const { result } = renderHook(() => useCounter(), { wrapper })
  act(() => {
    result.current.increment()
  })
  expect(result.current.count).toBe(2)
})
```

## isMounted Technique

- [GH Utility Module For this](https://github.com/jmlweb/isMounted)

only needs to be used AFTER an `await` statement checking `if (isMounted)` or
in the `catch` block of a try catch like `if (isMounted) console.log(error)`

## UseLayout

## useRef

```javascript
const inputEl = useRef(null)

return (
  <>
    <input ref={inputEl} type="text" />
  </>
)
```

## useState

`setState` does not auto merge update objects

to merge updates:

```javascript
setState(prevState => {
  // Object.assign would also work
  return { ...prevState, ...updatedValues }
})
```

## useRef Lottie Example For Animation

- [Medium Article](https://medium.com/@noamgjacobsonknzi/lottie-with-react-hooks-f52de4b6a2c4)
- [CodeSandbox](https://codesandbox.io/s/lottie-demo-react-hooks-b7pg4?from-embed)
