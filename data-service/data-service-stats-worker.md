---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 42.02643171806167
---

# Data Service Worker

Run with docker

```
docker build -t ds_worker:latest .

# Without environment variables
docker run -it ds_worker:latest

# With environment variable
docker run -it -e DB_HOST=172.17.0.1 ds_worker:latest
```

Environment variables

| APP\_LOGS                         | true                  | Enable logging                                                                        |
| --------------------------------- | --------------------- | ------------------------------------------------------------------------------------- |
| APP\_MIN\_HEIGHT                  | 1                     | Blockchain height from which worker starts synchronizing data                         |
| APP\_TRACK\_ALL\_ACCOUNTS         | true                  | Synchronize data for all blockchain accounts, even those that are not smart contracts |
| BLOCKCHAIN\_DAPP\_FATHER\_ADDRESS | <p><br></p>           | Address of blockchain account containing list of approved addresses                   |
| BLOCKCHAIN\_NODE\_URL             | http://localhost:6869 | Blockchain node url                                                                   |
| BLOCKCHAIN\_CHAIN\_ID             | R                     | Blockchain chain id                                                                   |
| DB\_NAME                          | admin                 | Database name                                                                         |
| DB\_HOST                          | localhost             | Database host                                                                         |
| DB\_PORT                          | 27017                 | Database port                                                                         |
| DB\_USERNAME                      | root                  | Database username                                                                     |
| DB\_PASSWORD                      | password              | Database password                                                                     |
| GRPC\_HOST                        | localhost             | Blockchain node GRPC service host                                                     |
| GRPC\_PEERS                       | <p><br></p>           | List of additional grpc nodes                                                         |
| GRPC\_UPDATES\_PORT               | 6881                  | Port of GRPC updates services                                                         |
| GRPC\_API\_PORT                   | 6877                  | Port of GRPC api services                                                             |
| REDIS\_QUEUE                      | default               | Name of redis queue                                                                   |
| REDIS\_HOST                       | localhost             | Redis host                                                                            |
| REDIS\_PORT                       | 6379                  | Redis port                                                                            |
| TEST\_DAPP\_FATHER\_SEED          | <p><br></p>           | Dapp father address used for testing                                                  |
| TEST\_GENESIS\_SEED               | <p><br></p>           | Seed for address with tokens used for testing                                         |
| TEST\_INTEGRATION\_DELAY          | 1200                  | Delay in milliseconds used for some tests                                             |
