---
description: >-
  Transfers key to other user (DAppFather tries to refill both accounts on
  success)
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# transferKey(recipient: String)

#### Params:

* `recipient` - address of recipient
* `key as payment` - key to send

#### Requirements:

* valid key (issuer, timestamp)
* key in users wallet

#### Error messages:

* `wrong asset count` - more or less than one asset provided as payment
* `wrong asset issuer` - asset issuer is other than Supplier
* `key expired` - timestamp in key description expired

```
func transferKey(recipient: String) ={
  let keyInfo = getAssetInfoFromPayment(i) # throws errors when wrong issuer or key is expired
  let recipientAddr = addressFromStringValue(recipient)
  let transfer = ScriptTransfer(recipientAddr,1,keyInfo.id)::[]
  (transfer, rechargeIfNeeded(recipientAddr) && rechargeIfNeeded(i.caller)) # transfer and recharge if needed
}
```
