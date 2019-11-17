# JEST MOCKS

## Summary

Notes on writing mocks with jest

## Resources

[Docs](https://jestjs.io/docs/en/mock-functions)
[Mock AWS SQS](https://itnext.io/mock-promisified-aws-service-operation-calls-with-jest-6f11a22a371)

## Mock NPM Package

```javascript
jest.mock("react-router-dom", () => ({
  ...jest.requireActual("react-router-dom"), // use actual for all non-hook parts
  useParams: () => ({
    id: "1"
  }),
  useRouteMatch: () => ({ url: "/id/1" })
}));
```

## Mock File

```javascript
import moduleName, { foo } from "../moduleName";

jest.mock("../moduleName", () => {
  return {
    __esModule: true,
    default: jest.fn(() => 42),
    foo: jest.fn(() => 43)
  };
});

moduleName(); // Will return 42
foo(); // Will return 43
```
