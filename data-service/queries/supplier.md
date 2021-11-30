---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# supplier

#### Arguments:

* `address - String!`

#### Response:

* `Supplier!`

### Example

#### Query:

```
query supplier($address: String!) {
  supplier(address: $address) {
    id
    address
    whitelisted
    name
    description
    whitelist
    organisations
    createdAt
    updatedAt
    score
  }
}
```

#### Variables:

`{"address": "xyz789"}`

#### Response

```
{
  "data": {
    "supplier": {
      "id": ID,
      "address": "xyz789",
      "whitelisted": true,
      "name": "abc123",
      "description": "abc123",
      "whitelist": ["abc123"],
      "organisations": ["abc123"],
      "createdAt": DateTime,
      "updatedAt": DateTime,
      "score": 123.45
    }
  }
}
```
