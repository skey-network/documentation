---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
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

#### Variables:

`{"id": "xyz789"}`

#### Response:

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
