# GRAPHQL ERRORS

## MetadataType fields must be an object with field names as keys or a function
which returns such an object.
No need to instanciate twice
```
const MetadataType = new GraphQLObjectType({
  name: 'MetadataType',
    fields: {
    appName: {
      type: GraphQLString,
    },
  },
});
```

```
metadata: {
  //type: new GraphQLObjectType(MetadataType), // WRONG
  type: MetadataType, // RIGHT
  resolve() {
  return {
    appName: 'myapp',
    appVersion: '5',
    };
  },
},
```
