---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# devices

#### Arguments:

* `order - String` - Order in which records will be sorted. Correct values are "`asc`" for ascending and "`desc`" for descending . Default = "`asc`"
* `orderBy - String` - Field name used for sorting. For example { order: "`desc`", orderBy: "`updatedAt`" } returns most recently updated items first
* `search - String` - Used to search for match in multiple fields. It appends a new field (score) to returned items. For example query devices { search: "`teltonika`", order: "`desc`", orderby: "`score`" } returns devices that have "teltonika" string in one of the fields and places best matches first
* `skip - Int` - Used for pagination. Indicates how many records starting from the first one should be skipped. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. `Default = 0`
* `take - Int` - Used for pagination. Indicates how many records should be returned in the current request. For example, { skip: 20, take: 10 } equals 3 page and 10 items for each page. Default value is 25. Maximum amount is 1000 . `Default = 25`
* `filter - DevicesFilter Default = {}`
* `geoSearch - GeoSearchInput` - Returns list of devices that are inside of selected rectangle. For example, for points \[lat:49, lng: 16] as bottomLeft and \[lat:54, lng:24] as upperRight, it's going to return all devices in Poland
* `geoSearchCircle - GeoSearchCircleInput` - Returns list of devices within radius of a selected point
* `keysOwner - String` - Returns list of devices to which an address has keys. For example, User with address user\_1 is the owner of keys key\_1 and key\_2, key\_1 is for device\_1 and key\_2 is for device\_2. There are also user\_2, device\_3 and key\_3. The method will return \[device\_1, device\_2]. This is helpful when user need a list of devices he can interact with
* `includeRemoved - Boolean` - By default the list will not include Devices which have been removed by the Supplier. To also get Devices removed, set this flag to true.  `Default = false`

#### Response:

Returns a `PaginatedDevices!`

### Example

#### Query:

```
query devices($order: String, $orderBy: String, $search: String, $skip: Int, $take: Int, $filter: DevicesFilter, $geoSearch: GeoSearchInput, $geoSearchCircle: GeoSearchCircleInput, $keysOwner: String, $includeRemoved: Boolean) {
  devices(order: $order, orderBy: $orderBy, search: $search, skip: $skip, take: $take, filter: $filter, geoSearch: $geoSearch, geoSearchCircle: $geoSearchCircle, keysOwner: $keysOwner, includeRemoved: $includeRemoved) {
    objects {
      ...DeviceFragment
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
  "orderBy": "xyz789",
  "search": "abc123",
  "skip": 0,
  "take": 25,
  "filter": {},
  "geoSearch": GeoSearchInput,
  "geoSearchCircle": GeoSearchCircleInput,
  "keysOwner": "xyz789",
  "includeRemoved": false
}
```

#### Response

```
{
  "data": {
    "devices": {
      "objects": [Device],
      "meta": Meta
    }
  }
}
```
