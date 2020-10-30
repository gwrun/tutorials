# Running pgAdmin4 with docker-compose
## Get started

1. Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

2. Copy ```.env.example``` file to ```.env```
```
$ cp .env.example .env
```
3. Configure your ```.env``` file

4. Create directory for pgAdmin data 

```
$ mkdir data
```

5. pgAdmin runs as the pgadmin user (UID: 5050) in the pgadmin group (GID: 5050) in the container. You must ensure that all files are readable, and where necessary (e.g. the working/session directory) writeable for this user on the host machine. For example:

```
$ sudo chown -R 5050:5050 data/
```

6. Run service
```
$ docker-compose up --build
```

- The `volume` setting in the `docker-compose.yml` defines local directory to expose to.
- pgAdmin documentation is available at [pgadmin.org/docs/](https://www.pgadmin.org/docs/).

## License

pgAdmin is released under the [PostgreSQL Licence](https://github.com/postgres/pgadmin4/blob/master/LICENSE), which is a liberal Open Source licence similar to BSD or MIT, and approved by the Open Source Initiative. The copyright for the project source code, website and documentation is attributed to the [pgAdmin Development Team](https://www.pgadmin.org/development/team/)
