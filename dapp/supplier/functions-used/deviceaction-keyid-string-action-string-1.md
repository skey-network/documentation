---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# deviceActionAs(keyID: String, action: String, keyOwner: String, mobileId: String)

Carries out some action on device using a Key owned by an Organisation (tries to refill account on success).

#### Params:

* `keyID - id of nft token`
* `action - action to be carried out`
* `keyOwner - address of Organisation owning the key`
* `mobileId - mobile ID of User performing the action`

#### Requirements:

* Valid key (timestamp, issuer)
* Key whitelisted in device's wallet
* Asset (key) in invoking user's wallet
* Account performing the action needs to be added to Organisation
* User account and Mobile ID in Organisation must match
* Organisation has to be added in Supplier data

#### **Error messages:**

* \[E1] Key not owned - Key not found in user's wallet
* \[E3] Wrong key issuer - Key issuer is other than Supplier
* \[E4] No such device -  There is no such device in Supplier dApp
* \[E5] Key not whitelisted - Key is not whitelisted in device's data
* \[E6] Device not connected
* \[E7] Device not active
* \[E8] Key expired
* \[E9] Not permitted by organization - User invoking the function is not a member of the Organisation
* \[E10] Mobile id not set - User invoking the function does not have Mobile ID set in Organisation
* \[E11] Id mismatch - Mobile ID of User does not match Mobile ID set in Organisation
* \[E12] Organization not permitted - Organisation not added to Supplier
* \[E19] Not a key - there is no asset with given id
* \[E20] Not a device key - there is no device info in key

```
func deviceActionAs(keyID: String, action: String, keyOwner: String, mobileId:String) = {
  let keyOwnerAddress = addressFromStringValue(keyOwner)
  let hasNoKey = assetBalance(keyOwnerAddress, fromBase58String(keyID)) < 1 # organisation has no key
  let allowedByKeyOwner = organizationWhitelisted(keyOwner) && whitelistedByOrganization(keyOwnerAddress, toBase58String(i.caller.bytes), mobileId)

  if (hasNoKey) then throw(EKeyNotOwned)
  else if(!allowedByKeyOwner) then throw(ENotPermittedByKeyOwner)
  else deviceActionWithKey(i,keyID, action) 
}
```
