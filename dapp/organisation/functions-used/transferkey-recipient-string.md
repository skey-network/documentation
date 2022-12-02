---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# setMobileId(id:String)

Sets mobile id if user is added to organisation and has no id specified.

#### Params:

* user written in organisation with '?' as mobile id

#### Error messages:

* \[E207] Forbidden id string - mobile id is forbidden string (?/\*)
* \[E210] Not a memberr - organisation has no such user
* \[E211] Cant change existing id - id was already set

```
func setMobileId(id:String)={
  # if unset && active member set
  # else error
  let actual = userKeyFromAddr(i.caller)
  if(actual==NONE)then throw(ENotAMember)
  else if(incorrectMobileId(id))then throw(EForbiddenIdStr)
  else if(userKeyFromAddr(i.caller)!=mobileIdUnset)then throw(ENoExistingIdChange)
  else{
    [StringEntry(userKeyFromAddr(i.caller),id)]
  }
}
```
