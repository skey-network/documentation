# Skey Bridge



Tool provided by the Skey Network at [https://bridge.skey.network/](https://bridge.skey.network/). It is used to exchange Skey on the Ethereum blockchain tokens to the Skey technical tokens (called SkeyUSD) on the Skey Network Blockchain.

It requires you to authenticate with Skey Keeper and connect to MetaMask - a software cryptocurrency wallet used to interact with the Ethereum blockchain.

The tool, before proceeding with the replacement operation, checks if:

* Metamask is connected
* Keeper is connected
* WVS chainId is valid
* ETH chainId is valid
* Oracle have enough tokens
* User have enough tokens

Before approving an operation, we will find out how many actions we will be able to carry out, including:

* devices creating
* keys creating
* a supplier account setting up
* devices updating
* a key transfering
* interacting with a device
* transferring tokens
