# GRAPHQL QUERIES

## Resources

[Aliases](https://medium.com/atheros/graphql-quick-tip-aliases-567303a9ddc5)
[Fragments](https://graphqlmastery.com/blog/how-to-query-your-schema-with-graphql-fragments)

## JOINS

(https://apihandyman.io/and-graphql-for-all-a-few-things-to-think-about-before-blindly-dumping-rest-for-graphql/)
GraphQL is really powerful but be warned that it’s not SQL nor an ETL, you
can select the data you want, aggregate queries, change names but not join
queries or change the data structure

### Accept Array of Strings as Argument

only query needs to change - resolver can still look like

```
async getTeam(root, { ids }) {
  getUsers(id: [ID]!): Users
}
```

# Return Array of Objects in Resolver

have to use a list type of the object

```
type Post {
  id: Int
  date: Float
  text: String
}

type PostList {
  total: Int
  filtered: Int
  posts: [Post]
}

type Query {
  posts(id: Ind, offset: Int, limit: Int, filter: String): PostList
}

schema {
  query: Query
}
```
