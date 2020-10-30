1. Create a new tunnel and store its tunnel secrets file into `secrets/tunnel.json`

2. Run service
```
$ docker-compose up --build
```

## initial configuration
- Grafana is configured to only be accessible using [gw.run](https://gw.run) secure tunnel in read-only mode. 
- Any user that you authorized for this tunnel will be able to see dashboards in read-only mode
- inside Grafana, do additional sign in with default admin/admin password to map more users

- The `volume` setting in the `docker-compose.yml` defines local directory to expose to.
- The Grafana documentation is available at [grafana.com/docs](https://grafana.com/docs/).
