---
expect_validation_error: true
---

# test-add-field-error

```graphql @server
schema {
  query: Query
}

type User {
  name: String
  address: Address
}
type Address {
  city: String
}

type Query @addField(name: "street", path: ["user", "address", "street"]) {
  user: User @http(path: "/user/1", baseURL: "http://localhost:8000")
}
```
