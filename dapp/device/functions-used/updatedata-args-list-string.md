---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# updateData(args:List\[String])

Updates data in device wallet.

#### Params:

List of actions written as string (max. 15 entries at once) in schema: `action#type#key#value`. Types of action set/delete.

* `action` - set (create new/update old entry), delete (remove entry)
* `type` - type of entry (int/string/bool), skip for delete
* `value` - value of entry or delete#key, skip for delete
* `key` - key of entry

#### Error messages:

* `[E103] Not permitted` - user is not device's Supplier

```
func updateData(args:List[String])={
  let supplierAddr = addressFromStringValue(getStrByKey(supplierKey))
  if(supplierAddr != i.caller)then throw("Not permitted")
  else FOLD<15>(args, [], updData)
}
```
