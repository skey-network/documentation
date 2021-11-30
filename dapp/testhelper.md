---
cover: ../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# TestHelper

#### Config

Default config looks like this:

```
{
  chainId:'R', 						// chain id - 'R' for local test node
  nodeUrl:'http://localhost:6869/', // url of waves node
  keyDuration:100000,     // how long key will be valid
  rechargeLimit:50,   // recharge limit
  initAccounts:true 				// generates random accounts
}
```

#### Accounts

* `Bank` - wallet used for charging other wallets
* `DevOwner` - owner of device
* `Dapp` - main script wallet
* `Device` -device which will be added
* `KeyOwner` - future owner of registered key
* `Dummy` - just to test that a non-registered user without any key can't do anything

#### Methods

* `createAndLogAccount(name:String)` - creates and logs account address in console
* `deployDapp(seed:String)` - compiles wallet.ride and deploys using provided seed
* `txSuccess(signedTx)` - broadcasts provided transaction, expects tx success
* `txDappFail(signedTx, expectedMessage)` - broadcasts provided transaction, expects dapp failure equal to provided message
* `dappValueFor(key:String)` - gets value for given key from dApp
* `walletValueFor(wallet:Account,key:String)` - gets value for given wallet from dApp
* `getNftFrom(wallet:Account, issuer: Account)` - gets list of nft from selected wallet by provided issuer
* `makeid(length)` - makes random id (used for addManyKeys test)

#### Balance

Helper contains an instance of BalanceTracker (accessible via helper.balance) responsible for tracking asset balance changes.

#### Methods

* `setDefaultAsset(defaultAsset:string)` - sets default asset
* `fetchCurrent(account:Account,asset:string)` - fetches current balance of given asset (not saving it)
* `setActual(account:Account, asset?:string)` - saves current balance of given/default asset for account
* `expectChange(account: Account, change: Number)` - expects change (positive/ zero/ negative) for default asset
* `expectChangeFor(account:Account, asset:string, change:Number)` - expects change (positive/ zero/ negative) for given asset
* `expectRise(account: Account, asset?: string)` - expects rise of asset count
* `expectFall(account: Account, asset?: string)` - expects fall of asset count

#### Run waves node locally:

`docker run -d -p 6869:6869 wavesplatform/waves-private-node`
