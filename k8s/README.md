# Kubenetes Configuration

These are the configuration files used to deploy the application.

## Deploying to DigitalOcean

First create a cluster with one machine.

Next install [`doctl`](https://github.com/digitalocean/doctl) and [`kubectl`](https://kubernetes.io/docs/tasks/tools/install-kubectl/) and run the following commands to deploy the app:

```sh
# Get k8s config and set it as the current context
doctl kubernetes cluster kubeconfig save <your_cluster_name>
# Create the namespace that the app runs in
kubectl create -f k8s/namespace.yaml
# Apply configs
kubectl apply -f k8s/secrets.yaml
kubectl apply -f k8s/deployment.yaml
```

## Updating a deployment

The config uses the latest image, so if you've tagged an pushed a new version all you need to do is scale down and up each deployment:

```sh
kubectl scale deployment/drand-relay-twitter-deployment --replicas=0 -n drand
kubectl scale deployment/drand-relay-twitter-deployment --replicas=1 -n drand
```