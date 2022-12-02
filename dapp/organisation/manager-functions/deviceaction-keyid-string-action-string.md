---
cover: ../../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# MNGAddUser(manager:String,address:String,mobileId:String,note:String)

Adds user to organisation as a Manager

#### Params:

* `mamanager` - Address of manager performing the action
* `address` - Address of user to add
* `mobileId` - Mobile ID of user to add
* `note` - Note about added account. For security reasons we recommend encrypting this value beforehand. It will be stored on the blockchain as-is. Provide an empty string to not set one.

#### Requirements:

* Manager has to be added to the Organisation
* Address cannot be added already
* Mobile ID needs to be unique

#### **Error messages:**

* \[E209] Not permitted
* \[E212] Incorrect user address

```
func MNGAddUser(manager:String,address:String,mobileId:String)={
  if(i.caller!=this)then throw(ENotPermitted) else{
    
    # with initial funds?
    match(addressFromString(address)){
      case t:Address =>[StringEntry(userKeyFromAddr(t),mobileId),ScriptTransfer(t,500000,unit)]
      case _ => throw(EIncorrectUserAddr)
    }
  }
}
```
