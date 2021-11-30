---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# key

#### Arguments:

* `assetId - String!`

#### Response:

* `Key!`

### Example

#### Query:

```
query key($assetId: String!) {
  key(assetId: $assetId) {
    id
    assetId
    issuer
    owner
    name
    device
    validTo
    issueTimestamp
    burned
    createdAt
    updatedAt
    whitelisted
    score
    deviceName
    deviceWhitelisted
  }
}
```

#### Variables

`{"assetId": "xyz789"}`

Response

```
{
  "data": {
    "key": {
      "id": ID,
      "assetId": "abc123",
      "issuer": "xyz789",
      "owner": "xyz789",
      "name": "abc123",
      "urządzenie": "xyz789",
      "validTo": 987.65,
      "issueTimestamp": 987.65,
      "burned": true,
      "createdAt": DateTime,
      "updatedAt": DateTime,
      "whitelisted": false,
      "score": 123.45,
      "deviceName": "xyz789",
      "deviceWhitelisted": true
    }
  }
}
```
