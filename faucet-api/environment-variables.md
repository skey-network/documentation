# Environment variables



| Parameter                       | Description                                           | Default Value                            |
| ------------------------------- | ----------------------------------------------------- | ---------------------------------------- |
| PORT                            | Port to run application on                            | 3000                                     |
| APP\_ENABLE\_STANDARD\_FAUCET   | Enable /faucet/refill/{address} endpoint              | true                                     |
| APP\_ENABLE\_CAPTCHA\_FAUCET    | Enable /faucet/refill\_with\_captcha endpoint         | false                                    |
| APP\_ENABLE\_KEY\_OWNER\_FAUCET | Enable /faucet/refill\_token\_owner endpoint          | false                                    |
| APP\_ENABLE\_AUTHORIZED\_FAUCET | Enable /faucet/refill\_authorized/{address} endpoint  | false                                    |
| BLOCKCHAIN\_NODE\_URL           | Blockchain node url                                   | http://localhost:6869                    |
| BLOCKCHAIN\_CHAIN\_ID           | Blockchain chain id                                   | R                                        |
| BLOCKCHAIN\_SEED                | Organisation address seed phrase (required)           | -                                        |
| FAUCET\_REFILL\_MAX\_AMOUNT     | Maximum amount of tokens while refilling              | 1                                        |
| CAPTCHA\_SECRET\_KEY            | Google reCaptcha v2 secret key                        | 6LeIxAcTAAAAAGG-vFI1TnRWxMZNFuojJ4WifJWe |
| FAUCET\_DAPP\_FATHER\_ADDRESS   | Dapp father address used for validation               | -                                        |
| FAUCET\_AUTHORIZED\_API\_KEY    | Api key used for validating refill\_authorized method | -                                        |

**NOTE**: Default Captcha key will verify anything, so make sure to set a different one in production!

Site key for default secret key: 6LeIxAcTAAAAAJcZVRqyHh71UMIEGNQ\_MXjiZKhI

**BLOCKCHAIN\_SEED** is required to start the app.

The app uses[ waves private node](https://github.com/wavesplatform/private-node-docker-image) by default. If you want to deploy the app to testnet, change those environment variables:

`export BLOCKCHAIN_NODE_URL='https://master.testnet.node.smartkeyplatform.io'`

`export BLOCKCHAIN_CHAIN_ID='A'`

and make sure you have funds on your account.
