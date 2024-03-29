---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# addKey(keyID: String)

Adds an existing NFT Key to device whitelist.

#### Params:

* `keyID` - id of NFT

#### Requirements:

* Invoking wallet must be owner of device or main dApp
* Key issued by Supplier dApp

#### Error messages:

* `[E102] Wrong key issuerr` - issuer of asset is other than Supplier
* `[E103] Not permitted` - user is not a device owner
* `[E104] This key is banned` - key is banned by Supplier
* `[E105] This key is already assigned`

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
