---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# KeysFilter

#### Field Names:

* `issuer - String`
* `owner - String`
* `name - String`
* `device - String`
* `burned - Boolean`
* `deviceWhitelisted - Boolean` - Filter keys by Supplier device whitelist. For example, if set to true, this will return only keys for devices that are whitelisted by their Suppliers. If set to false,it will return only keys for devices that are not whitelisted by their Suppliers.If not given, it's not filtered at all.

#### Example:

```
{
  "issuer": "abc123",
  "owner": "xyz789",
  "name": "xyz789",
  "device": "xyz789",
  "burned": false,
  "deviceWhitelisted": true
}
```
