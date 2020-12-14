How to self-host PGAdmin on local server or VM,
and provide a secure authenticated access to it over the internet using [gw.run](https://gw.run).

1. [Create a new tunnel](https://gw.run/) and store its tunnel secrets file into `secrets/tunnel.json`

2. Run service

```
$ docker-compose up --build
```

3. Open tunnel URL, authenticate with your email address and you shoudl see pgAdmin welcome screen

You would need additionally provide the admin user and password, both are configurable in `docker-compose.yml` :

```Docker
      - PGADMIN_DEFAULT_EMAIL=user@domain.com
      - PGADMIN_DEFAULT_PASSWORD=password
```

pgAdmin documentation is available at [pgadmin.org/docs/](https://www.pgadmin.org/docs/).
