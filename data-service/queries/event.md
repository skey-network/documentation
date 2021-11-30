---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# event

#### Arguments:

* `txHash - String!`

#### Response:

* `Event!`

### Example

#### Query:

```
query event($txHash: String!) {
  event(txHash: $txHash) {
    id
    txHash
    sender
    device
    assetId
    action
    status
    createdAt
    updatedAt
    score
  }
}
```

#### Variables:

`{"txHash": "abc123"}`

#### Response:

```
{
  "data": {
    "event": {
      "id": ID,
      "txHash": "xyz789",
      "sender": "abc123",
      "device": "abc123",
      "assetId": "abc123",
      "action": "abc123",
      "status": "xyz789",
      "createdAt": DateTime,
      "updatedAt": DateTime,
      "score": 123.45
    }
  }
}
```
