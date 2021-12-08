---
description: Removes key from device.
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# removeKey(keyID: String)

#### Params:

* `keyID` - id of nft token

#### Requirements:

* Address invoking wallet must be owner of device or main dApp

#### Error messages:

* `[E103] Not permitted` - User is not supplier/owner or key is banned/not added

```
func removeKey(keyID: String) = {
  let supplierAddr = addressFromStringValue(getStrByKey(supplierKey))
  let ownerAddr = addressFromStringValue(getStrByKey(ownerKey))
  if(supplierAddr==i.caller) then {       # supplier bans key
     [StringEntry(nftKey(keyID),INACTIVE)]
  } else if (ownerAddr==i.caller) then {  # user can remove not banned key
     let keyStatus = getStrByKey(nftKey(keyID))
     if(keyStatus == "active") then {           
      [DeleteEntry(nftKey(keyID))] # remove key from data
     } else {
       throw("Not permitted")
     }
  } else throw("Not permitted")
}

```
