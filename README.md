# GraphQL Yoga Template

Basic implementation of GraphQL server using [`graphql-yoga`](https://github.com/prisma/graphql-yoga)

## Querying

The query strings below can be used to test whether this template is functioning at the unique Glitch link of your project.

```json
query {
  hello
}
```

```json
query {
  hello (name: "John Wick")
}
```

### Basic Implementation

```js
import { GraphQLServer } from "graphql-yoga";
// ... or using `require()`
// const { GraphQLServer } = require('graphql-yoga')

const typeDefs = `
  type Query {
    hello(name: String): String!
  }
`;

const resolvers = {
  Query: {
    hello: (_, { name }) => `Hello ${name || "World"}`
  }
};

const server = new GraphQLServer({ typeDefs, resolvers });
server.start(() => console.log("Server is running on localhost:4000"));
```
