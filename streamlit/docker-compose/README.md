# Running a streamlit application with docker-compose

Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

```shell
$ docker-compose up --build
```

Streamlit is now running inside a docker-compose container, secure and inaccessible without authentication and authorization. 
You can safely access your application using gw.run tunnel.
