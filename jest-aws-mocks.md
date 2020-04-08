# JEST AWS MOCKS

## Summary

## Resources

- [Medium Post](https://medium.com/@windix/mock-aws-javascript-library-in-jest-8aad872c1468)

### Cognito

#### Mock Cognito Once

at base of file

```javascript
jest.mock('aws-sdk', () => ({
  ...jest.requireActual('aws-sdk'),
  CognitoIdentityServiceProvider: jest.fn().mockImplementation(() => ({
    listUsers: jest.fn().mockImplementation(() => ({
      promise: jest.fn(() => null),
    })),
  })),
}))
```

#### Mock Cognito Multiple Times

- [Example](https://github.com/dwyl/aws-sdk-mock/issues/127)

NOTE: doesn't actually use aws-sdk-mock package at all.
I was only able to get this to work with spyOn instead of the example above using jest.mock

```javascript
test('returns users', async () => {
  const awsMock = jest.spyOn(AWS, 'CognitoIdentityServiceProvider')
  awsMock.mockImplementation(() => {
    return {
      listUsers: jest.fn(() => ({
        promise: jest.fn(() => ({ Users: [] })),
      })),
    }
  })
  const res = await myUserLookup({
    userPoolId: '',
    filter: `email = "email@email.com"`,
  })

  expect(res).toEqual({ Users: [] })
})
```
