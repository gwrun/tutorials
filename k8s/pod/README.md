# Secure tunnel to any service running inside kubernetes container

If your Kubernetes cluster is deployed to one of the cloud providers, you may set up
an ingress, TLS certficate bot and OAuth authentication proxy that would interface with your service.

If your Kubernetes cluster is running on a local machine, then you have an additional complication.

[gw.run](https://gw.run/) provides a simple solution to all the above problems.

The below assumes a `microk8s` kubernetes distribution that is common for standalone VMs,
but it would work for any other kubernetes distribution.

1. First, reserve a domain name for your application and download certificate by visiting [gw.run admin panel](https://gw.run/)

2. You now should have a file called like `my-tunnel-gw-run.json`. Create a Kubernetes secret like that:

```bash
$ microk8s kubectl create secret generic my-tunnel-gw-run --from-file=tunnel.json=./my-tunnel-gw-run.json
secret/my-tunnel-gw-run created
```

3. Suppose we want to securely expose Kubernetes dashboard

```bash
$ microk8s kubectl get services --all-namespaces
NAMESPACE     NAME                        TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
default       kubernetes                  ClusterIP   10.152.183.1     <none>        443/TCP    17d
kube-system   metrics-server              ClusterIP   10.152.183.185   <none>        443/TCP    17d
kube-system   kubernetes-dashboard        ClusterIP   10.152.183.79    <none>        443/TCP    17d
kube-system   dashboard-metrics-scraper   ClusterIP   10.152.183.170   <none>        8000/TCP   17d
```

Make sure your cluster has DNS service enabled. In that case, the service would be accessible at `https://service.namespace`.

4. Deploy a tunnel

```bash
$ microk8s kubectl apply -f tunnel-pod.yaml
```

check out it started OK:

````bash
$

5. Visit tunnel URL (i.e. https://my-tunnel.gw.run) and you should see Kubernetes dashboard prompt

Now you need a token. See more

```bash
$ token=$(microk8s kubectl -n kube-system get secret | grep default-token | cut -d " " -f1)
$ microk8s kubectl -n kube-system describe secret $token
````

Voilà, you now can access your Kubernetes cluster dashboard from anywhere!
