# Run docker container

```
docker build -t faucet-api .
```

```
# on localhost
docker run -d --name faucet-api -p 3000:3000 -e BLOCKCHAIN_SEED='YOUR_SEED_PHRASE' faucet-api
```

```
# on testnet
docker run -d --name faucet-api -p 3000:3000 \
-e BLOCKCHAIN_SEED='YOUR_SEED_PHRASE' \
-e CAPTCHA_SECRET_KEY='YOUR_CAPTCHA_SECRET_KEY' \
-e BLOCKCHAIN_NODE_URL='https://master.testnet.node.smartkeyplatform.io' \
-e BLOCKCHAIN_CHAIN_ID='A' \
Faucet-api
```
