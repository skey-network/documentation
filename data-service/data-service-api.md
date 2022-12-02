---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# Data Service Api

Run with docker

`docker compose build && docker compose up`

Environment variables

|             Property            |     Default value    |             Description             |
| :-----------------------------: | :------------------: | :---------------------------------: |
|            APP\_PORT            |         3000         |       Port used by the server       |
| APP\_DEFAULT\_PAGINATION\_LIMIT |          25          | Number of items returned by default |
|   APP\_MAX\_PAGINATION\_LIMIT   |         1000         |   Maximal number of items returned  |
|      APP\_REQUIRE\_API\_KEY     |         true         |  Whether app should require api key |
|          APP\_API\_KEY          | super-secret-api-key |               Api key               |
|             DB\_NAME            |         admin        |            Database name            |
|             DB\_HOST            |       localhost      |            Database host            |
|             DB\_PORT            |         27017        |            Database port            |
|           DB\_USERNAME          |         root         |          Database username          |
|           DB\_PASSWORD          |       password       |          Database password          |
