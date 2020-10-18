# Running Plotly Dash apps with docker-compose


Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

```shell
$ docker-compose up --build
```

Note this example has to download ~80MB of data to render, and this will delay your start.

Note that in order to work properly in a `docker-compose` environment, you need instruct your Dash's Flask application to listen to host `0.0.0.0`, 
as by default Flask binds to `127.0.0.1` which is only accessible to `plotly` container. Note that we are not exposing any ports from the `plotly` container that runs your app, 
which means your application is only accessible via `gw.run` tunnel that requires user authentication. 

When running your app, make sure you control it with 