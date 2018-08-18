# GRAPHQL INTERFACES

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
`;

module.exports = interfaces;
```
