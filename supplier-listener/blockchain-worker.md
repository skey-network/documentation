---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# Blockchain Worker

### Running from sources:

Required packages: nodejs, npm (prefered instalation via nvm)

* Clone repository
* Navigate to `blockchain-worker` folder
* Install dependencies npm install
* Copy `.env.example` as .env, and modify its contents as in [Configuration file section](https://github.com/skey-network/listener-blockchain-worker#configuration-file);
* Run command `npm start`

### **Building and running docker image:**

#### Build

Execute command in project directory:

`docker build -t supplier-listener-blockchain-worker .`

Result should look like:

`(...) Successfully built IMAGE_ID`

#### Run

To run image execute (docker env as file or params is required):

`docker run -i <place docker envs here> IMAGE_ID`

If there is no env specified Blockchain Worker will stop execution.

#### Build and run

All-in-one command which will build image and run it (ensure that the path to config is correct).

`` docker run -i <place docker envs here> `docker build -q .` ``

#### Configuration file:

* `Running from sources` - it will expect .env in project folder.
* `Running in docker container` - it will expect env specified as docker env file or parameters.

#### BLOCKCHAIN

* dApp monitored for action requests:

`DAPP='3NBPqqjDH2eYmoHeXNPnHhLvA7D4UDQXQcx'`

* Functions called in dApp in order to make action on device (separated by "|"):

`DAPP_FUNCS='deviceAction|deviceActionAs'`

* Url to node used for monitoring state of dApp:

`NODE_URL='`[`https://nodes-testnet.wavesnodes.com`](https://nodes-testnet.wavesnodes.com)`'`

#### Options for HTTP mode

Number of blocks over parsed one higher values are safer but slower.

`SAFETY_LEVEL=0`

Checking interval for new transactions

`CHECK_INTERVAL=1000`

#### Options for GRPC mode

Blockchain updates extension port

`NODE_GRPC_EVENTS='localhost:6881'`

Grpc extension port

`NODE_GRPC='10.0.0.7:6877'`

#### Redis

Redis server address

`REDIS_HOST="127.0.0.1"`

Redis server port

`REDIS_PORT="6379"`
