---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# Environment variables

* `PORT` - Port to run the app

Example value - 3000

* `LOG_LEVEL` - Set log level. Available modes are ( none, standard, debug ). Logs are also saved in logs.txt file.

Example value - standard

* `ADMIN_EMAIL` - Admin email

Example value - admin@admin.com

* `ADMIN_PASSWORD` - Admin password

Example value - password

* `JWT_SECRET` - String to use for creating JWT tokens

Example value - aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa

* `JWT_VALID_TIME` - Time for which JWT token is valid

Example value - 1h

* `BLOCKCHAIN_SEED` - Blockchain dApp backup phrase

Example value - auto deposit have lake easy minute donkey solution okay account utility lady unusual actual idle

* `BLOCKCHAIN_NODE_URL` - Blockchain public node url

Example value - https://nodes-testnet.blockchainnodes.com

* `BLOCKCHAIN_CHAIN_ID` - Blockchain chain id. For example, testnet is 'T'.

Example value - T

* `SUPPLIER_URL` - IoT platform API url

Example value - https://liveobjects.Supplier-business.com/api/v1

* `SUPPLIER_API_KEY` - IoT platform API key

Example value - aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa

* FAUCET\_DEVICE - Amount of tokens to transfer when creating new device

Example value - 10000000

* `FAUCET_USER` - Amount of tokens to transfer when creating new user

Example value - 10000000

* `KEY_MIN_DURATION` - Minimal time in milliseconds when key is valid

Example value - 3600000

* `ENCRYPTION_SALT` - Salt phrase used to encrypt account seeds while creating blockchain accounts.

Example value - foobar

* `ENCRYPTION_IV` - Initial vector used to encrypt account seeds while creating blockchain accounts.

Example value - 0d8fa75738410842

* `DEVICE_SCHEMA_VERSION` - Version of device address schema(it's saved on the blockchain)

Example value - 1.0

* `CORS_ORIGIN` - CORS origin link

Example value -  [http://example.com](http://example.com)

