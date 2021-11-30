---
description: Adds key to device.
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# addKey(keyID: String)

#### Params:

* `keyID` - id of nft token

#### Requirements:

* Invoking wallet must be owner of device or main dApp
* Key issued by Supplier dApp

#### Error messages:

* `Wrong key issuer` - issuer of asset is other than Supplier
* `Not permitted` - user is not a device owner
* `This key is banned` - key is banned by Supplier
* `This key is already assigned`

```
###
#
# Write key entry:
# - key_{token_id}: "{device_address}"
#
@Callable(i)
func addKey(keyID: String) = {
  let callerAddress = toBase58String(i.caller.bytes)
  let keyInfo = getAssetInfo( fromBase58String(keyID))
  let supplierAddr = addressFromStringValue(getStrByKey(supplierKey))
  let ownerAddr = addressFromStringValue(getStrByKey(ownerKey))

  # let keyIsNotNft = match assetInfo(fromBase58String(keyID)) {
  #   case asset:Asset =>
  #       asset.decimals != 0 || asset.reissuable == true || asset.quantity != 1
  #   case _ => true
  # }


  # optional - check device in key (will not work with open when there is another dev address)
  if(keyInfo.issuer!=supplierAddr)then throw("Wrong key issuer") # accepted only keys issued by supplier
  else if ((ownerAddr!=i.caller) && (supplierAddr!=i.caller)) then throw("Not permitted") # only supplier can add key
  else if (nftValue(keyID) == INACTIVE && supplierAddr!=i.caller) then throw("This key is banned")
  else if (nftValue(keyID) == ACTIVE) then throw("This key is already assigned")
  else{
    [
     StringEntry(nftKey(keyID), ACTIVE)
    ]
  }
}

```
