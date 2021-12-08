---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# dAppFather

dAppFather is used to refill the target account if main asset is under a certain amount.

Data:

* `refill_amount` **** - amount which triggers refill and sets value of transfer
* `supplier_<address>` - address of Supplier, value: 'active'
* `org_<address>` - address of organization, value: 'active'

## **Functions Used:**

### refill(targetAddrStr:String)

Refills target account if main asset is under specified amount

#### **Params:**

* `targetAddrStr` - address of target

#### **Requirements:**

* caller is written as Supplier in data

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
    # if user cash is below some level
    ([
      ScriptTransfer(targetAddr,refillAmount, unit)
    ],true)
    }
  } else ([],false) #throw("supplier not auhorized")
  }
```

