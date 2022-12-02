---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# Data Service

Data Service is a publicly available server that each Supplier can optionally use in its server infrastructure. This tool allows the implementation of advanced filtering, sorting and aggregation of data.

Data Service functionality is based on communication via gRPC ([https://grpc.io/](https://grpc.io/) ). Skey nodes send information to subscribed data service workers about any changes happening on blockchain.

Data Service consistconsists of two elements connected to the same database:

* _Data Service Worker_ - its task is to subscribe to gRPC and filter relevant blockchain data and handle changes. It filters and reacts to state updates such as transfers, issuing new keys, dApp invocations, data entries etc. Changes are saved in a structured form in the mongoDB database.
* _Data Service API_ - an application used to retrieve data from a database. It has no possibility to modify or create new documents. It uses graphQL interfaces to create multiple queries and pipelines for example fetching the list of devices that the selected address has access to.

The communication is authenticated using the api key added as the http header - for example:

`{ "x-api-key": "superhiper=secret=key" }`
