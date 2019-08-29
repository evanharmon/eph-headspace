# GRAPHQL INTERFACES

## Resources

[Unions And Interfaces](https://graphqlmastery.com/blog/graphql-interfaces-and-unions-how-to-design-graphql-schema)

## Nested Interfaces

```
const interfaces = `
  interface MetadataInterface {
    appName: String
  }

  interface DBlockInterface {
    OrderNo: String
  }

  interface PayloadInterface {
    d: DBlockInterface
  }
`

module.exports = interfaces
```
