---
description: Adds many keys (80 max) in one invoke.
---

# addManyKeys(args:List\[String])

#### Params:

* List of keys

#### Error messages:

* `Not permitted` - User is not device's supplier

```
func addManyKeys(args:List[String])={
  let supplierAddr = addressFromStringValue(getStrByKey(supplierKey))
  if(supplierAddr != i.caller)then throw("Not permitted")
  else FOLD<80>(args, [], addKeys)
}
```
