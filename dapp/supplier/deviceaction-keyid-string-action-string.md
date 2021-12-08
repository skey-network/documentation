---
description: Carries out some action on device (tries to refill account on success);
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# deviceAction(keyID: String, action: String)

#### Params:

* `keyID` - id of nft token
* `action` - action to be carried out

#### Requirements:

* Valid key (timestamp, issuer)
* Key whitelisted in device's wallet
* Asset (key) in invoking user's wallet

#### **Error messages:**

* `[E1] Key not owned` - Key not found in user's wallet
* `[E3] Wrong key issuer` - Key issuer is other than Supplier
* `[E4] No such device` - There is no such device in Supplier dApp
* `[E5]Key not whitelisted` - Key is not whitelisted in device's data
* `[E6]Device not connected`
* `[E7] Device not active`
* `[E8] Key expired`
* `[E19] Not a key` - there is no asset with given id
* `[E20] Not a device key` - there is no device info in key

```
func deviceAction(keyID: String, action: String) = {
  let keyOwnerAddress = i.caller
  let hasNoKey = assetBalance(keyOwnerAddress, fromBase58String(keyID)) < 1 # organisation has no key
  
  if (hasNoKey) then throw("Key not owned")
  else deviceActionWithKey(i,keyID, action) 
}
```
