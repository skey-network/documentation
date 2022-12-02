---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# addManyKeys(args:List\[String])

Adds many keys (80 max) in one invocation.

#### Params:

* List of keys

#### Error messages:

* `[E103] Not permitted` - User is not device's supplier

```
func addManyKeys(args:List[String])={
  let supplierAddr = addressFromStringValue(getStrByKey(supplierKey))
  if(supplierAddr != i.caller)then throw("Not permitted")
  else FOLD<80>(args, [], addKeys)
}
```
