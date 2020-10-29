# ENZYME

## Summary

Notes on working with the enzyme testing framework for react

## Resources

- [Docs](https://enzymejs.github.io/enzyme/)
- [Jest Setup](https://enzymejs.github.io/enzyme/docs/guides/jest.html)
- [Enzyme SetupTests With Jest](https://github.com/enzymejs/enzyme/blob/master/docs/guides/jest.md)

### Re-Use Jest Mocks

- [Setup Tests](https://medium.com/@side_swail/setting-up-enzyme-with-jest-8b3b2ab207dc)
- [Jest SetupTestsAfterEnv](https://jestjs.io/docs/en/configuration#setupfilesafterenv-array)

package.json

```json
{
  "jest": {
    "setupFilesAfterEnv": ["<rootDir>src/setupTests.js"]
  }
}
```
