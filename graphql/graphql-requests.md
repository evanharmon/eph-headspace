# GRAPHQL REQUESTS

## Summary

Notes on http requests in graphql

## Resources

- [Response Shape](https://graphql.org/learn/serving-over-http/)
- [Example Axios Graphql Request](https://medium.com/@stubailo/how-to-call-a-graphql-server-with-axios-337a94ad6cf9)

## HTTP Response Shape

```json
{
  "data": { ... },
  "errors": [ ... ]
}
```

## Example Mutation With Axios

```javascript
axios
  .post('http://myapiendpoint', {
    query: `
      mutation addSkill($id:String!, $name:String!, $level:String!, $type:String!) {
        mutation addSkill(id:$id, name:$name", level:$level, type:$type) {
          status
          id
          name
          level
          type
        }
      }
    `,
    variables: {
      id: '1234',
      name: 'Evan'
      level: 'intermediate',
      type: 'bass',
    },
  })
```
