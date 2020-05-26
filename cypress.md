# CYPRESS

## Summary

Notes on using cypress.io E2E testing tool

## Resources

- [E2E With Cypress and Auth0](https://auth0.com/blog/end-to-end-testing-with-cypress-and-auth0/)
- [Single Sign On Recipe](https://github.com/cypress-io/cypress-example-recipes/tree/master/examples/logging-in__single-sign-on)
- [Testing Library Docs](https://testing-library.com/docs/cypress-testing-library/intro)
- [Testing Library Examples](https://github.com/testing-library/cypress-testing-library/tree/master/cypress/integration)

## Docker Install

```docker
RUN npm install --global --allow-root --unsafe-perm=true cypress
```

## Open Cypress

```console
cypress open --project ./
```

## Install Testing Library Support

```console
npm install --save-dev cypress @testing-library/cypress
```
