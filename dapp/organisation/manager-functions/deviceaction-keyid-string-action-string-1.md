---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# MNGTransferToken(manager:String,token:String,recipient:String,amount:Int)

Transfer Activation Token(s) as a Manager.

#### Params:

* `manager` - Address of Manager performing the action
* `token` - Asset ID of Activation Token to send
* `recipient` - Address of Activation Token Recipient
* `amount` - Amount of Activation Tokens to send

#### Requirements:

* Manager has to be added to the Organisation
* Amount has to be a positive number
* Organisation has to have sufficient amount of Activation Tokens on it’s wallet

#### **Error messages:**

* \[E209] Not permitted
* \[E212] Incorrect user address
* \[E213] Not an asset
* \[E214] Not issued by organisation\


```
func MNGTransferToken(manager:String,token:String,recipient:String,amount:Int) = {
  if(i.caller!=this)then throw(ENotPermitted) else{
    let tokenId = fromBase58String(token)
    let tokenInfo = match(assetInfo(tokenId)){
      case t:Asset => t
      case _ => throw(ENotAnAsset)
    }
    let address = match (addressFromString(recipient)) {
        case t:Address => t 
        case _ => throw(EIncorrectUserAddr)
    }
    
    if(tokenInfo.issuer != this) then throw(ENotIssuedByOrganization)
    else [ScriptTransfer(address,amount,tokenId)] 
  }
}

```
