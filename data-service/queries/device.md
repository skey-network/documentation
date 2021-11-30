---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# Device

#### Arguments:

* `address - String!`

#### Response:

* Returns a `Device!`

### Example

#### Query:

```
query device($address: String!) {
  device(address: $address) {
    id
    address
    supplier
    owner
    name
    description
    lat
    lng
    alt
    location {
      ...LocationFragment
    }
    distance
    visible
    active
    connected
    removed
    details {
      ...DetailsFragment
    }
    custom
    whitelist
    createdAt
    updatedAt
    whitelisted
    score
  }
}

```

#### Variables:

`{"address": "xyz789"}`

#### Response:

```
{
  "data": {
    "device": {
      "id": ID,
      "address": "abc123",
      "supplier": "abc123",
      "owner": "abc123",
      "name": "xyz789",
      "description": "abc123",
      "lat": 123.45,
      "lng": 123.45,
      "alt": 987.65,
      "location": Location,
      "distance": 123.45,
      "visible": true,
      "active": true,
      "connected": true,
      "removed": true,
      "details": Details,
      "custom": "abc123",
      "whitelist": ["abc123"],
      "createdAt": DateTime,
      "updatedAt": DateTime,
      "whitelisted": true,
      "score": 987.65
    }
  }
}
```
