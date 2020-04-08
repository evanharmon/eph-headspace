# JEST

## Summary

Notes on testing with Jest

## Resources

- [Github Cheatsheet](https://github.com/sapegin/jest-cheat-sheet)
- [Debug In Chrome](https://jestjs.io/docs/en/troubleshooting)
- [Async Examples](https://github.com/facebook/jest/tree/master/examples/async)

### Expect

#### Check If Array Contains String

```javascript
expect(['mic', 'synth']).toContain('synth')
```

#### Check If Array Contains Property

[Medium Match Object In Array](https://medium.com/@andrei.pfeiffer/jest-matching-objects-in-array-50fe2f4d6b98)

```javascript
expect(state).toEqual(
  expect.arrayContaining([
    expect.objectContaining({
      type: 'END',
    }),
  ])
)
```

#### DeepEqual Equivalent

[.toMatchObject()](https://jestjs.io/docs/en/expect#tomatchobjectobject)

### Testing Errors

#### Test That Function Throws Error

function must be wrapped in an anonymous function

```javascript
it('fails early when AWS credential properties are missing', () => {
  expect(() => signRequest({})).toThrow()
})
```

#### Promise Function Should Reject

```javascript
test('errors if property not supplied', async () => {
  expect.assertions(1)
  await expect(myfunction({})).rejects.toEqual('name property must be supplied')
})
```

### CSS / SASS

Enable importing scss / sass files

inside package.json

```json
{
  "jest": {
    "moduleNameMapper": {
      "\\.(css|less|sass|scss)$": "<rootDir>/__mocks__/styleMock.js",
      "\\.(gif|ttf|eot|svg)$": "<rootDir>/__mocks__/fileMock.js"
    }
  }
}
```
