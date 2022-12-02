---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# Environment variables

|      Variable name      |                                           Example value                                          |                                                 Description                                                 | Required |
| :---------------------: | :----------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------: | -------- |
|           PORT          |                                               3000                                               |                                             Port to run the app                                             | NO       |
|        LOG\_LEVEL       |                                             standard                                             |      Set log level. Available modes are ( none, standard, debug ). Logs are also saved in logs.txt file     | NO       |
|       ADMIN\_EMAIL      |                                          admin@admin.com                                         |                                             Admin e-mail address                                            | YES      |
|     ADMIN\_PASSWORD     |                                             password                                             |                                                Admin password                                               | YES      |
|       JWT\_SECRET       |                                          jwtsecretstring                                         |                        JSON Web Token(JWT) secret phrase for authorisation encryption                       | YES      |
|     JWT\_VALID\_TIME    |                                                1h                                                | Time period after which JSON Web Token expires - default is 24h. Value should be compliant with this format | NO       |
|         DB\_KEY         |                                            supplierAPI                                           |                                             SQLite database key                                             | NO       |
|         DB\_PATH        |                                           ./db.sqlite3                                           |                                     Relative path to the SQLite database                                    | YES      |
|     BLOCKCHAIN\_SEED    | auto deposit have lake easy minute donkey solution okay account utility lady unusual actual idle |                                        Supplier wallet backup phrase                                        | YES      |
|  BLOCKCHAIN\_NODE\_URL  |      [https://nodes-testnet.blockchainnodes.com](https://nodes-testnet.blockchainnodes.com)      |                                URL to the Skey Network public blockchain node                               | YES      |
|  BLOCKCHAIN\_CHAIN\_ID  |                                                 T                                                |                                     Chain ID of Skey Network blockchain                                     | YES      |
|      SUPPLIER\_URL      |                  [https://supplier.example.com/](https://supplier.example.com/)                  |                                             IoT Platform API URL                                            | YES      |
|    SUPPLIER\_API\_KEY   |                                           iotexamplekey                                          |                                             IoT Platform API key                                            | NO       |
|      FAUCET\_DEVICE     |                                             10000000                                             |                               Number of Skeylets to transfer to created device                              | NO       |
|       FAUCET\_USER      |                                             10000000                                             |                                Number of Skeylets to transfer to created user                               | NO       |
|    KEY\_MIN\_DURATION   |                                              3600000                                             |      Minimal time in milliseconds for which created Skey Network Keys can be valid - default is 1 hour      | NO       |
|     ENCRYPTION\_SALT    |                                          examplesalt123                                          |              Salt phrase used to encrypt saved account seeds when creating blockchain accounts              | YES      |
|      ENCRYPTION\_IV     |                                         0d8fa75738410842                                         |       Initialisation Vector(IV) used to encrypt saved account seeds when creating blockchain accounts       | YES      |
| DEVICE\_SCHEMA\_VERSION |                                                1.0                                               |                          Version of device address schema (saved on the blockchain)                         | NO       |
|       CORS\_ORIGIN      |                [http://supplier.api.example.com](http://supplier.api.example.com)                |                                      CORS origin link - default is “\*”                                     | NO       |

