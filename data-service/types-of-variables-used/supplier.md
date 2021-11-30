---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# Supplier

#### Field Names:

* `id - ID!`
* `address - String!`
* `whitelisted - Boolean!`
* `name - String`
* `description - String`
* `whitelist - [String!]!`
* `organisations - [String!]!`
* `createdAt - DateTime`
* `updatedAt - DateTime`
* `score - Float`

#### Example:

```
{
  "id": ID,
  "address": "xyz789",
  "whitelisted": true,
  "name": "xyz789",
  "description": "abc123",
  "whitelist": ["xyz789"],
  "organisations": ["xyz789"],
  "createdAt": DateTime,
  "updatedAt": DateTime,
  "score": 987.65
}
```
