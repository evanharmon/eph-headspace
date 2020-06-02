# REACT TESTING

## Summary

Notes on tools, frameworks, etc for React testing

## Resources

[React Testing Library](https://testing-library.com/docs/react-testing-library/api#render-options)
[Jest Expect](https://jestjs.io/docs/en/expect)
[Testing React-Router](https://github.com/ReactTraining/react-router/blob/master/packages/react-router/docs/guides/testing.md)
[Shallow Renderer](https://reactjs.org/docs/shallow-renderer.html)
[Kent C Dodds Testing Javascript Course](https://testingjavascript.com)

## Test Initial State

not react specific, simple javascript class property testing and using `expect`
from jest

```javascript
const component = new CollectionForm({ props: {} })
expect(component.state.redirectTo).toBeNull()
```
