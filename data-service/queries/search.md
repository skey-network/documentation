---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# search

#### Arguments:

* `skip - Int` - Used for pagination. Indicates how many records starting from the first one should be skipped. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. . Default = `0`
* `take - Int` - Used for pagination. Indicates how many records should be returned in the current request. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. Default value is 25. Maximum amount is 1000 . Default = `25`
* `input - String!`

#### Response:

* `SearchResults!`

### Example

#### Query:

```
query search($skip: Int, $take: Int, $input: String!) {
  search(skip: $skip, take: $take, input: $input) {
    devices {
      ...DeviceFragment
    }
    events {
      ...EventFragment
    }
    keys {
      ...KeyFragment
    }
    organisations {
      ...OrganisationFragment
    }
    suppliers {
      ...SupplierFragment
    }
    meta {
      ...MetaFragment
    }
  }
}
```

#### Variables:

`{"skip": 0, "take": 25, "input": "xyz789"}`

#### Response

```
{
  "data": {
    "search": {
      "devices": [Device],
      "events": [Event],
      "keys": [Key],
      "organisations": [Organisation],
      "suppliers": [Supplier],
      "meta": Meta
    }
  }
}
```
