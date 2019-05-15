# JEST

## Summary

Notes on testing with Jest

## Error watching file for changes: EMFILE

`brew install watchman`

## Resources

[Github Cheatsheet](https://github.com/sapegin/jest-cheat-sheet)

## Error Your Test Suite Must Contain At Least One Test

jest cli testRegex is probably including snapshots

```console
jest --testRegex MyComponent.test.js
```

should be

```console
jest --testRegex MyComponent/MyComponent.test.js
```
