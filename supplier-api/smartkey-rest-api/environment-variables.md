---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# Environment variables

|      Variable name      |                                           Example value                                          |                                                 Description                                                 | Required |
| :---------------------: | :----------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------: | :------: |
|           PORT          |                                               3000                                               |                                             Port to run the app                                             |          |
|        LOG\_LEVEL       |                                             standard                                             |      Set log level. Available modes are ( none, standard, debug ). Logs are also saved in logs.txt file     |          |
|       ADMIN\_EMAIL      |                                          admin@admin.com                                         |                                             Admin e-mail address                                            | REQUIRED |
|     ADMIN\_PASSWORD     |                                             password                                             |                                                Admin password                                               | REQUIRED |
|       JWT\_SECRET       |                                          jwtsecretstring                                         |                        JSON Web Token(JWT) secret phrase for authorisation encryption                       | REQUIRED |
|     JWT\_VALID\_TIME    |                                                1h                                                | Time period after which JSON Web Token expires - default is 24h. Value should be compliant with this format |          |
|         DB\_KEY         |                                            supplierAPI                                           |                                             SQLite database key                                             |          |
|         DB\_PATH        |                                           ./db.sqlite3                                           |                                     Relative path to the SQLite database                                    | REQUIRED |
|     BLOCKCHAIN\_SEED    | auto deposit have lake easy minute donkey solution okay account utility lady unusual actual idle |                                        Supplier wallet backup phrase                                        | REQUIRED |
|  BLOCKCHAIN\_NODE\_URL  |      [https://nodes-testnet.blockchainnodes.com](https://nodes-testnet.blockchainnodes.com)      |                                URL to the Skey Network public blockchain node                               | REQUIRED |
|  BLOCKCHAIN\_CHAIN\_ID  |                                                 T                                                |                                     Chain ID of Skey Network blockchain                                     | REQUIRED |
|      SUPPLIER\_URL      |                   [https://supplier.example.com/](https://supplier.example.com)                  |                                             IoT Platform API URL                                            | REQUIRED |
|    SUPPLIER\_API\_KEY   |                                           iotexamplekey                                          |                                             IoT Platform API key                                            |          |
|      FAUCET\_DEVICE     |                                             10000000                                             |                               Number of Skeylets to transfer to created device                              |          |
|       FAUCET\_USER      |                                             10000000                                             |                                Number of Skeylets to transfer to created user                               |          |
|    KEY\_MIN\_DURATION   |                                              3600000                                             |      Minimal time in milliseconds for which created Skey Network Keys can be valid - default is 1 hour      |          |
|     ENCRYPTION\_SALT    |                                          examplesalt123                                          |              Salt phrase used to encrypt saved account seeds when creating blockchain accounts              | REQUIRED |
|      ENCRYPTION\_IV     |                                         0d8fa75738410842                                         |       Initialisation Vector(IV) used to encrypt saved account seeds when creating blockchain accounts       | REQUIRED |
| DEVICE\_SCHEMA\_VERSION |                                                1.0                                               |                          Version of device address schema (saved on the blockchain)                         |          |
|       CORS\_ORIGIN      |                [http://supplier.api.example.com](http://supplier.api.example.com)                |                                      CORS origin link - default is “\*”                                     |          |

Example value -  [http://example.com](http://example.com)

