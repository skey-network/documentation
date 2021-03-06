---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# keys

#### Arguments:

* `order - String` - Order in which records will be sorted. Correct values are "asc" for ascending and "desc" for descending . Default = "`asc`"
* `orderBy - String` - Field name used for sorting. For example { order: "desc", orderBy: "updatedAt" } returns last updated items first
* `search - String` - Used to search for match in multiple fields. It appends a new field (score) to returned items. For example query devices { search: "teltonika", order: "desc", orderby: "score" } returns devices that have "teltonika" string in one of the fields and places best matches first
* `skip - Int` - Used for pagination. Indicates how many records starting from the first one should be skipped. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. . Default = `0`
* `take - Int` - Used for pagination. Indicates how many records should be returned in the current request. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. Default value is 25. Maximum amount is 1000 . Default = `25`
* `filter - KeysFilte`r - Default = {}

#### Response:

* `PaginatedKeys!`

### Example

#### Query:

```
query keys($order: String, $orderBy: String, $search: String, $skip: Int, $take: Int, $filter: KeysFilter) {
  keys(order: $order, orderBy: $orderBy, search: $search, skip: $skip, take: $take, filter: $filter) {
    objects {
      ...KeyFragment
    }
    meta {
      ...MetaFragment
    }
  }
}
```

#### Variables:

```
{
  "order": "asc",
  "orderBy": "xyz789",
  "search": "abc123",
  "skip": 0,
  "take": 25,
  "filter": {}
}
```

#### Response:

```
{
  "data": {
    "keys": {
      "objects": [Key],
      "meta": Meta
    }
  }
}
```
