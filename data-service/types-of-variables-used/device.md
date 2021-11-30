---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# Device

#### Field Names:

* `id - ID!`
* `address - String!`
* `supplier - String`
* `owner - String`
* `name - String`
* `description - String`
* `lat - Float`
* `lng - Float`
* `alt - Float`
* `location - Location`
* `distance - Float` - Returned only when fetching Devices from a circle using geoSearchCircle. This is the distance between the Device and a chosen point measured in meters.
* `visible - Boolean`
* `active - Boolean`
* `connected - Boolean`
* `removed - Boolean`
* `details - Details`
* `custom - String`
* `whitelist - [String!]!`&#x20;
* `createdAt - DateTime`
* `updatedAt - DateTime`
* `whitelisted - Boolean`
* `score - Float`

#### Example:

```
{
  "id": ID,
  "address": "abc123",
  "supplier": "xyz789",
  "owner": "abc123",
  "name": "abc123",
  "description": "xyz789",
  "lat": 987.65,
  "lng": 987.65,
  "alt": 987.65,
  "location": Location,
  "distance": 123.45,
  "visible": false,
  "active": true,
  "connected": true,
  "removed": true,
  "details": Details,
  "custom": "xyz789",
  "whitelist": ["abc123"],
  "createdAt": DateTime,
  "updatedAt": DateTime,
  "whitelisted": true,
  "score": 987.65
}
```
