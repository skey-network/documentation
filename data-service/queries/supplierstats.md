---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# supplierStats

#### Arguments:

* `id - String!`

#### Response:

* `SupplierMainDocument!`

### Example

#### Query:

```
query supplierStats($id: String!) {
  supplierStats(id: $id) {
    id
    type
    current {
      ...SupplierSubDocumentFragment
    }
    historical {
      ...SupplierSubDocumentFragment
    }
  }
}
```

#### Variables

`{"id": "xyz789"}`

#### Response

```
{
  "data": {
    "supplierStats": {
      "id": "xyz789",
      "type": "abc123",
      "current": SupplierSubDocument,
      "historical": [SupplierSubDocument]
    }
  }
}
```
