# refill(targetAddrStr:String)

Refills target account if main asset is under specified amount.

#### **Params:**

* `targetAddrStr` - address of target

#### **Requirements:**

* caller is written as Supplier or Organisation in data

```
func refill(targetAddrStr:String) = {
  let callerStrAddr = toBase58String(i.caller.bytes)
  let targetAddr = addressFromStringValue(targetAddrStr)
  let refillAmount = getRefillAmount()
  let refill = shouldRefill(targetAddr, refillAmount)
  if(activeAsSupplier(callerStrAddr)||activeAsOrg(callerStrAddr)) then {
    if(!refill)then {
      ([],false)
    }else{
    # if user asset balance is below specified level
    ([
      ScriptTransfer(targetAddr,refillAmount, unit)
    ],true)
    }
  } else ([],false) 
  }
```
