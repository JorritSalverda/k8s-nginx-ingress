
To make sure you can execute the RBAC roles and bindings make sure your own account is admin in the Kubernetes cluster.

```
ACCOUNT=$(gcloud info --format='value(config.account)')
kubectl create clusterrolebinding owner-cluster-admin-binding \
    --clusterrole cluster-admin \
    --user $ACCOUNT
```

To run nginx ingress controller at it's cheapest - yes with possible downtime - execute the following command:

```
cat kubernetes.yaml | kubectl apply -f -
```
