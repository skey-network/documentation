---
description: Adds a device if it has not already been added.
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# addDevice(deviceAddr: String)

#### Params:

* `deviceAddr` - address of the device to be added

#### Requirements:

* has to be called from the dApp wallet

```
func addDevice(deviceAddr: String) = {
  let userStatus = userStatusValue(toBase58String(i.caller.bytes))
  let ownerAddress = getDeviceOwnerAddressValue(addressFromStringValue(deviceAddr))
  let callerAddress = toBase58String(i.caller.bytes)
  let price = getNumberByKey(devicePriceKey)
  let assetId = getAssetId() # may be replaced later with const

  if(i.payments.size() < 1) then throw("wrong payments count")
  else if(i.payments[0].assetId != assetId) then throw("wrong asset, supported only xyz")
  else if(i.payments[0].amount != price) then throw("wrong payment value, expected " + toString(price))
  else if(userStatus == NONE) then throw("user not registered")
  else if(userStatus == BANNED) then throw("user banned")
  else if(ownerAddress != callerAddress) then throw("not an owner")
  else if(deviceStatusValue(deviceAddr) != NONE ) then throw("device already added")
  else{
    [
     StringEntry(deviceStatusKey(deviceAddr),CLOSED), # todo, device initial status?
     IntegerEntry(deviceCounterKey(deviceAddr), 0)
    ]
  }
}

```
