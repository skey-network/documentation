---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 42.80469897209985
---

# IoT Worker

### Running from sources:

Required packages: nodejs, npm (prefered instalation via nvm)

* Clone repository
* Navigate to `iot-worker` folder
* Install dependencies `npm install`
* Copy .env.example as .env, and modify its contents as in [Configuration file section](https://github.com/skey-network/listener-iot-worker#configuration-file)
* Copy device config c`onfig.json.example` as `config.jsonm` and modify it's contents as in [Devices configuration file section](https://github.com/skey-network/listener-iot-worker#devices-configuration-file)
* Run command `npm start`

### Building and running docker image

#### Build

Execute command in project directory:

`docker build -t supplier-listener-iot-worker .`

Result should look like:

`(...)`

`Successfully built IMAGE_ID`

#### Run

To run image execute (config.json and docker env as file or params are required):

``docker run -i -v `pwd`/.config.json:/app/config.json <place docker envs here> IMAGE_ID``

When `config.json` file is in another location, provide absolute path to it on left side of ":" (instead of \`pwd\``/config.json`, where pwd returns actual working directory, eg `/user/home/xyz/listener/config.json`).

If there is no env specified, Iot Worker will stop execution.

#### Build and run

All-in-one command which will build image and run it (ensure that path to config is correct)

`` docker run -i -v `pwd`/config.json:/app/config.json <place docker envs here> `docker build -q .` ``

#### Configuration file:

* Running from sources – It will expect `.env` and `config.json` in project folder.
* Running in docker container - path to `config.json` file should be provided as described in this section, including the rest of env specified as docker env file or parameters.

#### IoT

Token for IoT:

`IOT_PLATFORM_TOKEN='abcdef...'`

Url for sending command to devices where, for example {device\_address} will be replaced with device's blockchain address (more variables are available as specified below)

`IOT_PLATFORM_URL='http://localhost:3000/{device_address}/commands'`

Method used for requests:

`IOT_METHOD='POST'`

Variables available for url/json

* `device_address` - blockchain address of device
* `action_name` - name of requested action (command)
* `key_id` - id of key asset
* `function_name` - name of used function
* `device_model` - type of device

#### Redis

Redis server address

`REDIS_HOST="127.0.0.1"`

Redis server port

`REDIS_PORT="6379"`

#### Devices configuration file

Devices configuration is defined in config.json in JSON format (remove comments before use).

* `"devices"` – array of supported devices
* `"supportedAction"` – array of supported action for device
* `"json"` - json for request
* `"jsonByAction"` - request json can be dependent on action:
  * `"action"` - action to override json
  * `"json"` - json to be used instead

Example of configuration:

```
[
  {
    "devices": ["fmb920", "fmb900"],
    "supportedActions": ["open"],
    "json": "{\"command\": \"login passw setdigout 1? 1\"}"
  },
  {
    "devices": ["anyDev", "testDev"],
    "supportedActions": ["close", "open"],
    "json": "{...}",
    "jsonByAction": [
      { "action": "close", "json": "{\"payload\":\"testdev close json\"}" }
    ]
  }
]

```
