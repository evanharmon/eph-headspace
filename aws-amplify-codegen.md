# AWS AMPLIFY CODEGEN

## Summary

Notes on working with codegen from amplify cli

## Codegen File Dependencies

reads values from `.graphqlconfig.yml` and `amplify/#current-cloud-backend/amplify-meta.json`

`codegen` command will use `amplify-meta.json` API ID and graphql endpoint if
this file doesn't match the `.graphqlconfig.yml`!!

## Codegen Is Not Creating Queries / Mutations / Subscriptions

`amplify/#current-cloud-backend/amplify-meta.json` and
`amplify/backend/amplify-meta.json` should have the same API values
