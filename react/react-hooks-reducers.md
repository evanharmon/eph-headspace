# REACT HOOKS REDUCERS

## Summary

Notes on using useReducer with react hooks

## Resources

- [Docs](https://reactjs.org/docs/hooks-reference.html#usereducer)
- [CSS Tricks Example](https://css-tricks.com/getting-to-know-the-usereducer-react-hook/)
- [SO Test useReducer](https://stackoverflow.com/questions/59275441/how-test-a-component-using-the-usereducer-hook)

## Example Tests

Basic function test

```
it('returns new state for "update" type', () => {
  const initialState = [1];
  const updateAction = {type: 'update', newState: [1, 2, 3] };
  const updatedState = fooReducer(initialState, udpateAction);
  expect(updatedState).toEqual([1, 2, 3]);
});
```

useReducer test

```
it('should render as many divs as there are items', () => {
  act(() => {
    const { result } = renderHook(() => useReducer(FooReducer, [1]));
    const [state, dispatch] = result.current;
    dispatch({type: 'update', newState: [1, 2, 3]});
  });

  expect(state).toEqual([1, 2, 3]);
  // or expect(state).toHaveLenth(3) if you prefer
});
```
