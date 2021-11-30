---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# keyChart

#### Arguments:

* `id - String!`
* `begin - Float!` - Unix timestamp in milliseconds establishing the date when to start the chart. For example,to draw a monthly chart starting in January 2021 use 1609459200000
* `n - Int!` - Number of objects to be returned for chart. For example, to draw a monthly chart, use 30
* `length - Float!` - Amount of time in milliseconds from one time period to another. For example, to draw a monthly chart, use 1 day (86400000 milliseconds)

#### Response:

* `[KeyChartDocument!]!`

### Example

#### Query:

```
query keyChart($id: String!, $begin: Float!, $n: Int!, $length: Float!) {
  keyChart(id: $id, begin: $begin, n: $n, length: $length) {
    index
    timestamp
    data {
      ...KeysDataFragment
    }
  }
}
```

#### Variables:

`{"id": "abc123", "begin": 987.65, "n": 123, "length": 123.45}`

#### Response:

```
{
  "data": {
    "keyChart": [
      {
        "index": 987,
        "timestamp": 987.65,
        "data": KeysData
      }
    ]
  }
}
```
