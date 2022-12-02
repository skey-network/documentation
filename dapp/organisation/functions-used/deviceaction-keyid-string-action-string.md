---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# activate(id: String)

activates organisation user, writes its mobile id

#### Payments:

* activation token

#### Requirements:

* activation token must be whitelisted
* mobile id must be string other than '?' and '\*'

#### **Error messages:**

* \[E202] Wrong payments count - more or less than 1 payments attached
* \[E203] Wrong asset - wrong asset sent as payment
* \[E207] Forbidden id string - id string cannotcant be \* or ?
* \[E208] Activation failed, token is inactivee - asset was deactivated

```
func activate(id:String) = {
  let token = getPaymentSingleToken(i.payments)
  if(incorrectMobileId(id))then throw(EForbiddenIdStr)
  else if(checkTokenActive(token.id)) then {
    [
      StringEntry(userKeyFromAddr(i.caller), id)
    ]
  } else throw(EActivationTokenInactive)
}
```
