# Share files with Minio

If you want to share access to a local folder(s) to a group of people,
consider using `min.io` embedded web server which provides a nice embedded web server

[Create a new tunnel](https://gw.run/) and store its tunnel secrets file into `secrets/tunnel.json`

Then

```shell
$ docker-compose up --build
```

- The `volume` setting in the `docker-compose.yml` defines local directory to expose.
- this deployment runs `min.io` with default tokens, use `minioadmin` for both when requested after passing email-based authorization
