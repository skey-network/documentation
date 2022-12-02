---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# removeKey(key: String)

Removes key to device from organisation’s wallet

#### Params:

* `keyID - id of nft token`

#### Requirements:

* Invoked by owner of device or supplier

#### **Error messages:**

* \[E201] Not a key" - there is no token with given asset id
* \[E204] Not a device key - asset is not a device key
* \[E205] Not an owner address - owner address in token is incorrect
* \[E206] Owner not specified in device - device has no owner address specified
* \[E209] Not permitted - if invoking user is not supplier/owner of device\


```
func removeKey(key:String) = {
  let token = fromBase58String(key)
  let tokenInfo = getTokenInfo(token)
  let devOwner = getOwnerFromKey(tokenInfo)
  if(tokenInfo.issuer!=i.caller && devOwner !=i.caller && this !=i.caller)then throw(ENotPermitted) # added self
  else{
    [Burn(token,1)]
  }
}
```
