# AWS AMPLIFY GRAPHQL

## Summary

Notes on using aws amplify graphql services sdk's, cli, etc

## Project Structure

Do not edit anything in the build folder
`amplify/backend/api/myproject/build`

## Edit Schema

Edit the schema located at:
`amplify/backend/api/myproject/schema.graphql`

## Override Resolver

Create a folder called resolvers in `amplify/backend/api/myprojectname/resolvers`

Assuming a mutation exists in
`amplify/backend/api/myprojectname/build/resolvers/Mutation.createUser.request`,
add a custom resolver with a similar name like below:

`amplify/backend/api/myprojectname/resolvers/Mutation.createUser.req.vtl`

## Codegen Error Missing Backend

`ENOENT: no such file or directory, open /Users/eharmon/code/izotope/transfer-plus/amplify/#current-cloud-backend/amplify-meta.js`
copy from backend folder

```console
mkdir -p ./amplify/#current-cloud-backend
cp ./amplify/backend/amplify-meta.json ./amplify/\#current-cloud-backend
```
