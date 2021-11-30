---
cover: ../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# Unique Worker

#### **Build**Running from sources

Required packages: nodejs, npm (prefered instalation via nvm):

* Clone repository
* Navigate to iot-worker folder
* Install dependencies `npm install`
* Copy `.env.example` as .env, and modify its contents as in [Configuration file section](https://github.com/skey-network/listener-unique-worker#configuration-file)
* Run command `npm start`

### Building and running docker image

#### Build

Execute command in project directory:

`docker build -t supplier-listener-unique-worker .`

Result should look like:

`(...)`

`Successfully built IMAGE_ID`

#### Run

To run image execute (config.json and docker env as file or params are required):

`docker run -i <place docker envs here> IMAGE_ID`

If there is no env specified Unique Worker will stop execution.

#### Build and run

All-in-one command which will build image and run it (ensure that path to config is correct):

`` docker run -i <place docker envs here> `docker build -q .` ``

#### Configuration file:

* Running from sources - It will expect .env & config.json in project folder.
* Running in docker container - path to config.json file should be provided as described in [this section](https://github.com/skey-network/listener-unique-worker/blob/master/Building-and-running-docker-image), including rest of env specified as docker env file or parameters.

#### Redis

**Red**is server address

`REDIS_HOST="127.0.0.1"`

Redis server port

`REDIS_PORT="6379"`
