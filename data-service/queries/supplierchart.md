---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# supplierChart

#### Arguments:

* `id - String!`
* `begin - Float!` - Unix timestamp in milliseconds indicating the date when to start the chart. For example, to draw a monthly chart starting in January 2021 use 1609459200000
* `n - Int!` - Number of objects to be returned for chart. For example, to draw a monthly chart, use 30
* `length - Float!` - Amount of time in milliseconds from one time period to another. For example, to draw a monthly chart, use 1 day (86400000 milliseconds)

#### Response:

* `[SupplierChartDocument!]!`

### Example

#### Query:

```
query supplierChart($id: String!, $begin: Float!, $n: Int!, $length: Float!) {
  supplierChart(id: $id, begin: $begin, n: $n, length: $length) {
    index
    timestamp
    data {
      ...SuppliersDataFragment
    }
  }
}
```

#### Variables:

`{"id": "xyz789", "begin": 123.45, "n": 987, "length": 123.45}`

#### Response:

```
{
  "data": {
    "supplierChart": [
      {
        "index": 123,
        "timestamp": 987.65,
        "data": SuppliersData
      }
    ]
  }
}
```
