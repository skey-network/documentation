---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# suppliers

#### Arguments:

* `order - String` - Order in which records will be sorted. Correct values are "asc" for ascending and "desc" for descending . Default = "`asc`"
* `orderBy - String` - Field name used for sorting. For example { order: "desc", orderBy: "updatedAt" } returns last updated items first
* `search - String` - Used to search for match in multiple fields. It appends a new field (score) to returned items. For example query devices { search: "teltonika", order: "desc", orderby: "score" } returns devices that have "teltonika" string in one of the fields and places best matches first
* `skip - Int` - Used for pagination. Indicates how many records starting from the first one should be skipped. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. Default = `0`
* `take - Int` - Used for pagination. Indicates how many records should be returned in the current request. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. Default value is 25. Maximum amount is 1000 . Default = `25`;
* `filter - SuppliersFilter` Default = {}

#### Response:

* `PaginatedSuppliers!`

### Example

#### Query:

```
query suppliers($order: String, $orderBy: String, $search: String, $skip: Int, $take: Int, $filter: SuppliersFilter) {
  suppliers(order: $order, orderBy: $orderBy, search: $search, skip: $skip, take: $take, filter: $filter) {
    objects {
      ...SupplierFragment
    }
    meta {
      ...MetaFragment
    }
  }
}
```

#### Variables

```
{
  "order": "asc",
  "orderBy": "abc123",
  "search": "xyz789",
  "skip": 0,
  "take": 25,
  "filter": {}
}
```

#### Response

```
{
  "data": {
    "suppliers": {
      "objects": [Supplier],
      "meta": Meta
    }
  }
}
```
