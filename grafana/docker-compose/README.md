How to self-host Grafana on local server or VM,
and provide a secure authenticated access to it over the internet using [gw.run](https://gw.run).

1. [Create a new tunnel](https://gw.run/) and store its tunnel secrets file into `secrets/tunnel.json`

2. Run Grafana

```
$ docker-compose up --build
```

3. Open the tunnel URL and you should see Grafana welcome screen
   Do additional sign in with default admin/admin password to change default administration credentials
   and create more users with creation rights.

Grafana documentation is available at [grafana.com/docs](https://grafana.com/docs/)
