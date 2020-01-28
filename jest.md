# JEST

## Summary

Notes on testing with Jest

## Resources

[Github Cheatsheet](https://github.com/sapegin/jest-cheat-sheet)
[Debug In Chrome](https://jestjs.io/docs/en/troubleshooting)

## Error watching file for changes: EMFILE

```console
brew install watchman
```

## Run Single Test File

```console
jest --testRegex MyComponent.test.js
```

## Error: Your Test Suite Must Contain At Least One Test

jest cli testRegex is probably including snapshots

```console
jest --testRegex MyComponent.test.js
```

should be

```console
jest --testRegex MyComponent/MyComponent.test.js
```

## Debug Jest Test With Inspector

```console
node --inspect node_modules/.bin/jest --runInBand
```

## Hide Coverage On Jest Run

```console
jest --testRegex mycomponent.test.js --coverage=false
```

## Expect

### Check If Array Contains String

```javascript
expect(['mic', 'synth']).toContain('synth')
```

### Check If Array Contains Property

[Medium Match Objet In Array](https://medium.com/@andrei.pfeiffer/jest-matching-objects-in-array-50fe2f4d6b98)

```javascript
expect(state).toEqual(
  expect.arrayContaining([
    expect.objectContaining({
      type: 'END',
    }),
  ])
)
```
