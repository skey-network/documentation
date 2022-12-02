# Schema of creating new SubAccount for payment Card in blockchain

1\. Input card details POST [http://51.83.131.123:30330/v1/card](http://51.83.131.123:30330/v1/card)

Example payload send via form:

```
{
  "publicKey": "4s1NSh7cwCEjfcqT33QfpR6M5YjoyBMGiC8YjFqXiwgs",
  "expirationDate": "12/2023",
  "par": "50019D67OVBYUMPPJB33HHJTY4SIZ",
  "truncatedPan": "123456xxxxxx5432"
}
```

where `publicKey` belongs to users' main account from mobile APP.



2\. Generate a new blockchain account for a new card. More info how to do it:

```
// install this:
// https://github.com/skey-network/skey-libs
// npm install https://github.com/skey-network/skey-libs
// or
// yarn add https://github.com/skey-network/skey-libs

import { getInstance } from "skey-lib";

const instance = getInstance({
  nodeUrl: "https://master.nodes.skey.network",
  chainId: "M",
});

/** FOR TESTNET:
*
* const instance = getInstance({
*   nodeUrl: "https://master.testnet.node.smartkeyplatform.io",
*   chainId: "A",
* });
*
**/

const account = instance.createAccount();

// object account has 4 properties:
// - private Key
// - public Key
// - address
// - seed phrase used to generate the rest

/* Account example:
{
  seed: 'planet apple copy roast master obtain awake turn fiber trial spot absurd soccer strong come',
  privateKey: '83QNuuDh6Hsuhrkn9eC3GY4w4D6NYEbT1UXRGaQafS3y',
  publicKey: 'GFZdTJbhgZbXaMqmpstpo8te2CUCHgCBndsdQqxw14ph',
  address: '3EDewzt34nhV3LocfgqZ7omz6uFSJ6zEt8d'
}
```



3\. Get tokens which will be used as a fee on next steps. You have to send a POST request to:

* [https://faucet.skey.network/faucet/refill\_authorized/{address}](https://faucet.skey.network/faucet/refill\_authorized/%7Baddress%7D) \[MAINNET]
* [https://dev.faucet.smartkeyplatform.com/refill\_authorized/{address}](https://dev.faucet.smartkeyplatform.com/refill\_authorized/%7Baddress%7D) \[TESTNET]

where:

* `address` is an address of new blockchain account for the CARD
* `x-api-key` is static and will be send in another message

Faucet documentation is available here:\
[ https://faucet.skey.network/#/faucet/FaucetController\_refillAuthorized](https://faucet.skey.network/#/faucet/FaucetController\_refillAuthorized)

This will allow the card owner and TSS to perform actions on the account.





4\. Add entries into data storage of CARD account with public keys of Main User account and TSS account. These accounts will be able to perform actions on the Card account.

You can do it via data transaction, example:

```
import { getInstance } from "skey-lib";
import * as Transactions from "@waves/waves-transactions";
import * as Crypto from "@waves/ts-lib-crypto";

const chainId = "M"; // "A" for testnet

const instance = getInstance({
  nodeUrl: "https://master.nodes.skey.network", // https://master.testnet.node.smartkeyplatform.io for testnet.
  chainId,
});

const tssPublicKey = "..."; // public key of TSS account authorized to open
const publicKey = "4s1NSh7cwCEjfcqT33QfpR6M5YjoyBMGiC8YjFqXiwgs"; // request payload in 1)
const account = instance.createAccount(); // see 2)

// Faucet the account before executing code below - see 3)

const dataTx = Transactions.data(
  {
    data: [
      {
        key: "owner", // owner of subaccount
        type: "string",
        value: publicKey, // base58 string
      },
      {
        key: "authorised", // account authorized to invoke 'deviceAction'
        type: "string",
        value: tssPublicKey, // base58 string
      },
      {
        key: "card", // account generated for card
        type: "string",
        value: account.publicKey, // base58 string
      },
      {
        key: "status",
        type: "string",
        value: "active",
      },
      {
        key: "type",
        type: "string",
        value: "subAccount",
      },
      {
        key: "subType",
        type: "string",
        value: "paymentCard",
      },
      {
        key: "version",
        type: "string",
        value: "1",
      },
      {
        key: "details",
        type: "string",
        value: JSON.stringify({
          truncatedPan: "123456xxxxxx5432",
          provider: "mastercard",
        }),
      },
    ],
    fee: 10 ** 5,
    chainId,
  },
  account.seed
);

instance
  .broadcast(dataTx)
  .then(() => {
    console.log("data set successfully!");
  })
  .catch((e) => {
    console.error("something went wrong: ", e);
  });

```



5\. Set script to CARD account. How to do it:

```
// after performing 5)

// This is an example - not a working script
const script = "base64:whatever";

const scriptTx = Transactions.setScript(
  {
    script,
    chainId: "M", // "A" for testnet
    fee: 10 ** 6,
  },
  account.seed
);

instance
  .broadcast(dataTx)
  .then(() => {
    console.log("script set successfully!");
  })
  .catch((e) => {
    console.error("something went wrong: ", e);
  });
```

Script in RIDE is available on github:

* link to plain script:[ https://github.com/skey-network/dApps/blob/master/ride/card\_wallet.ride](https://github.com/skey-network/dApps/blob/master/ride/card\_wallet.ride)
* link to base64 script:[ https://github.com/skey-network/dApps/blob/master/compiled/card.txt](https://github.com/skey-network/dApps/blob/master/compiled/card.txt)



6\. Add params to webView url to handle response in mobile application.

* address new CARD address
* result Response 200 or error code
