---
cover: .gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# Glossary

_Skey Network Ecosystem_ - a set of open source licensed tools that enable providers to delegate access to their IoT assets via blockchain.

_Supplier_ - a service provider that, by design, has its own IoT platform that communicates with physical devices and provides the API needed to communicate with, for example with front-end applications such as administration panels and mobile applications.

_dApp_ - Decentralised application on a blockchain network owned by the Supplier.

_Oracle_ - Skey Network Ecosystem's set of tools for Suppliers, which includes Supplier API and Listener. The ecosystem creates a set of servers that are used to pull data from the Internet and store it on the blockchain in a smart contract form. These tools are intended to provide a bridge between the blockchain and the Supplier's IoT platform.

_Supplier API_ - is one of Skey Network's components that allows the Supplier’s dApp to be managed. It allows for example:

* creation of new accounts for devices in the blockchain, known as wallets
* moderation of devices' metadata such as name, description, geolocation
* management of the devices' keys ( creating, transferring, blocking, assigning expiry time).

_Listener_ - One of Skey Network's Oracle components. Listens for an event in the Supplier's dApp and sends a command to the Supplier's IoT platform.

_Data Service_ - A publicly available server that each Supplier can optionally deploy in its server infrastructure. This tool allows the implementation of advanced filtering, sorting and aggregation of data.

_Skey Network Node_ - a server which stores a copy of the complete blockchain. Each Supplier maintains a blockchain network by deploying a Node Skey Network in its infrastructure.

_Explorer_ - Skey Network’s block explorer. It is a developer's tool acting as a search engine for wallets' addresses or transactions. It allows the account balance, number of tokens held and transaction tracking to be viewed.

_Key Manager_ - an administration panel for Supplier API, which the Supplier can optionally place in his server infrastructure. Suppliers can replace Key Manager with their own IoT Platform management tool and extend it with Supplier Api maintenance.

_Device key_ - NFT token generated by the Supplier, using the Supplier API, for a certain device's wallet. Only users who have it in their wallet will be able to run scripts in the blockchain which are responsible for executing actions on the device.
