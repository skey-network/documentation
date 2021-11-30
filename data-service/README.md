---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# Data Service

Data Service is a publicly available server that each Supplier can optionally use in its server infrastructure. This tool allows the implementation of advanced filtering, sorting and aggregation of data.

Data Service functionality is based on communication with gRPC ([https://grpc.io/](https://grpc.io) ). Using the gRPC, Nodes Skey Network send information about changes to subscribers.

Data Service application consists of two elements connected to the same database:

* _Data Service Worker_ - its task is to subscribe to gRPC and then filter the relevant blockchain data and catch changes. Changes are saved in a structured form in the database.
* _Data Service Api_ - an application used to retrieve data from a database. It has no possibility to modify or save this data. It uses graphQL interfaces to create multiple queries and pipelines for example fetching the list of devices that the selected address has access to.

A Data Service Stats Worker is also provided as an additional process that is executed periodically for statistics updates. This tool updates the data stored in the database, such as the number of devices, the number of keys for each Supplier, etc.

The communication is authenticated using the api key added as the http header - for example:

`{ "x-api-key": "superhiper=secret=key" }`

The Data Service documentation has been made available using GraphQL Playground **** and can be found in the right-hand menu at [https://dev.v3.data-service.smartkeyplatform.io/graphql](https://dev.v3.data-service.smartkeyplatform.io/graphql) .
