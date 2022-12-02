---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# requestKey(deviceAddr: String, duration: Int)

Creates key for device if possible.

* If no price is specified in the "key\_price" entry, such a key cannot be purchased
* Can only be purchased by the owner of the device ('owner' entry in the device)
* A default token payment equal to `<key_price> * <time in minutes>` **** is required
* The validity of such a key is calculated from the date of purchase

#### Params:

* `deviceAddr` - address of device
* `duration` - time in minutes

#### Requirements:

* price per minute defined in device
* user is owner of device
* the payment amount is equal

#### Error messages:

* `[E13] Not an owner` - device not owned by user
* `[E14] Wrong price`- wrong amount of asset
* `[E16] Wrong payment` - supported only native token
* `[E17] Wrong payment value, expected <value>`
* `[E21] Price not specified in device`
* `[E22] Owner not specified in device`

```
func requestKey(deviceAddr: String, duration: Int) = {
  let issuedAt=lastBlock.timestamp
  let validUntil=issuedAt + duration * oneMinute
  let deviceOwner = ownerFromDevice(addressFromStringValue(deviceAddr))
  let keyPriceConstant = keyPriceFromDevice(addressFromStringValue(deviceAddr)) # throws if no price is specified
  let keyPrice = keyPriceConstant * duration
  let assetId = getAssetId()

  if(toBase58String(i.caller.bytes)!=deviceOwner)then throw("Not permitted")
  else if(deviceActionKey(deviceAddr)==NONE) then throw("No such device")
  else if(priceIsWrong(i,assetId,keyPrice))then throw("wrong price")
  else{
    let issue = Issue("SkeyNetwork",deviceAddr+"_"+validUntil.toString()+"_"+version1,1,0,false) # timestamp of issue is in token details
    let newAssetId = calculateAssetId(issue)
    ([
      issue,
      ScriptTransfer(i.caller,1,newAssetId)
    ], rechargeIfNeeded(i.caller))
  } 
}
```
