# AWS AMPLIFY

## Summary

Notes on using aws amplify sdk's, cli, etc

## Resources

- [AWS Blog Analytics None DataSource Subscriptions](https://aws.amazon.com/blogs/mobile/visualizing-big-data-with-aws-appsync-amazon-athena-and-aws-amplify/)
- [React Router Amplify Auth](https://www.rockyourcode.com/custom-react-hook-use-aws-amplify-auth/)
- [API Call Jest Mock Example](https://github.com/aws-amplify/amplify-js/blob/master/packages/api/__tests__/API-test.ts)

## Get Environment After Git Clone

```console
amplify env add
```

asks if you want to add an existing, displays list of envs from `team-provider-info.json`
choose existing environment

now do:

```console
amplify env checkout `env_name` --restore
```

This step adds the necessary amplify files that are in the gitgnore and not stored in the repo

## Pinpoint Errors

[GH Issue](https://github.com/aws-amplify/amplify-js/issues/3489)

disable Analytics in Amplify configure:

```javascript
Amplify.configure({
  Auth: {
    region: config.region,
    userPoolId: config.userPoolId,
    userPoolWebClientId: config.userPoolWebClientId,
    authenticationFlowType: 'USER_PASSWORD_AUTH',
  },
  Analytics: {
    disabled: true,
  },
})
```

## Configuration

Amplify Web Apps exhibit odd behavior around authentication 401's / 400's if
configuration is changed after loading. For now, tracking `authMode` of AppSync
in a seperate variable in the app to use after sign in.

## Install Specific Package

```console
npm install @aws-amplify/auth --save
```

## Import Specific Package

```javascript
import { graphql } from '@aws-amplify/Api'
```

## Jest Mock Example

```javascript
jest.mock('aws-amplify', () => {
  return {
    _esModule: true,
    Storage: {
      get: jest.fn(() => {}),
    },
    Hub: {
      listen: jest.fn(() => {}),
      remove: jest.fn(() => {}),
    },
  }
})
```
