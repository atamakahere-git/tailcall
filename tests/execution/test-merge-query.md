# test-merge-query

```graphql @server
schema @server(port: 3000) @upstream(baseURL: "http://abc.com") {
  query: Query
}

type Query {
  hello: String @expr(body: "world")
}
```

```graphql @server
schema @server(port: 8000) @upstream(proxy: {url: "http://localhost:3000"}) {
  query: Query
}

type Query {
  hi: String @expr(body: "world")
}
```
