# GRAPHQL MUTATIONS

## Example Mutation
```
mutation {
  myMutationName(
    id: "1234"
  ) {
    id
    testfield
    testobject {
      testid
      testfieldforobject
    }
  }
}
```
