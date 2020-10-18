# Running Plotly Dash apps with docker-compose


Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

```shell
$ docker-compose up --build
```

In order to work properly in a `docker-compose` environment, you need instruct your Dash's Flask application to listen to host `0.0.0.0` in the `app.py`
as by default Flask binds to `127.0.0.1` which is only accessible to `plotly` container. We are not exposing any ports from the `plotly` container that runs your app, 
which means your application is only accessible via `gw.run` tunnel that requires user authentication. 

```python
if __name__ == "__main__":
    app.run_server(host="0.0.0.0", port=8050, debug=True)
```

