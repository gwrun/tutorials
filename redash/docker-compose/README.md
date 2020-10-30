How to self-host [redash](https://redash.io) using docker-compose, and provide secure shared access to its instance using [gw.run](https://gw.run)

1. [Create a new tunnel](https://gw.run/admin) and store its tunnel secrets file into `secrets/tunnel.json`

2. Initialize database data for Redash
Run this command once to initialize the database
```
$ docker-compose run server create_db
```

3. Run service
```
$ sudo docker-compose up --build
```

Note:
- Redash depends on the two volumes for Redis and PostgreSQL - see `docker-compose.yml` if you want to customize its location
- Redash documentation is available at [redash.io/help](https://redash.io/help).
