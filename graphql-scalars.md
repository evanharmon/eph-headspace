# GRAPHQL SCALARS

## Date Scalar Type
```
const { GraphQLScalarType } = require('graphql');
const { Kind } = require('graphql/language');

module.exports = {
  Date: new GraphQLScalarType({
    name: 'Date',
    description: 'Custom scalar type for date object',
    parseValue: value => new Date(value),
    serialize: value => value.getTime(),
    parseLiteral: ast =>
    ast.kind === Kind.INT ? parseInt(ast.value, 10) : null,
  }),
};
```
