---
cover: ../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# Data Service Stats Worker

Run in development

```
yarn install

# Without environment variables
npm run dev -- current

# With environment variable
DB_HOST=172.17.0.1 npm run dev -- current
```

Run with docker

```
docker build -t stats-worker .

# Without environment variables
docker run -it stats-worker current

# With environment variable
docker run -it -e DB_HOST=172.17.0.1 stats-worker current
```

Parameters

| Parameters |      Description      | Default value |
| :--------: | :-------------------: | :-----------: |
| Positional | current or historical |       -       |

Environment variables

|   Parameter  |    Description    | Default value |
| :----------: | :---------------: | :-----------: |
|   DB\_NAME   |   Database name   |     admin     |
|   DB\_HOST   |   Database host   |   localhost   |
| DB\_USERNAME | Database username |      root     |
|   DB\_PORT   |   Database port   |     27017     |
| DB\_PASSWORD | Database password |    password   |
