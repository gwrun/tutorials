How to self-host Jupyter Voila interactive application
and provide a secure authenticated access to it over the internet using [gw.run](https://gw.run). 

1. [Create a new tunnel](https://gw.run/admin) and store its tunnel secrets file into `secrets/tunnel.json`

2. Run service
```
$ docker-compose up
```

3. Open tunnel URL, authenticate with your email address and you should see the sample application running in a little while, as it will need to fetch some data on a first run

[Jupyter Voila](https://jupyter.org/) allows you to convert any python notebook into an interactive application. 
