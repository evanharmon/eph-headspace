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
