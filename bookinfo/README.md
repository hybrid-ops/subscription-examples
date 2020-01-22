# bookinfo mcm artifacts

1. create the bookinfo projects / and other prereqs

```bash
kubectl apply -f prereqs.yaml
kubectl apply -f prereqs-ns.yaml
kubectl apply -f ip.yaml
```

2. define the channel that references the channel source, a helm repo, implemented as a github repo. The best practice is for `channels` to be in a common namespace. Not anyone should be able to modify a channel. In this example, the channel is created in the namespace `bookinfo-entitlement`.

```bash
kubectl apply -f bookinfo-channel.yaml
```

3. create the application, subscription and placement rule. Customize the bookinfo deployment.

```bash
kubectl apply -f bookinfo-app.yaml
```

4. after creating, nothing should happen if the `placement policies` are NOT met. Go label a managed cluster with the label `environment=Demo` and the helm chart will be deployed to that managed cluster.

