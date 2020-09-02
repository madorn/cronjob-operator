# cronjob-operator (without webhooks)
CronJob Operator example from book.kubebuilder.io

## Prerequisites

- [go](https://golang.org/dl/) version v1.13+.
- [docker](https://docs.docker.com/install/) version 17.03+.
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) version v1.11.3+.
- [kustomize](https://sigs.k8s.io/kustomize/docs/INSTALL.md) v3.1.0+
- Access to a Kubernetes v1.11.3+ cluster.

## Running locally

Install the CRDs into the cluster:

```
make install
```

Run the controller:

```
make run
```

Apply the `CronJob` CR to the cluster:

```
kubectl apply -f config/samples/
```

Verify a pod is created every 60 seconds:

```
kubectl get pods
```

## Running in a Cluster

Build and push your image to the location specified by `IMG`:

```
make docker-build docker-push <some-registry>/<project-name>:tag
```

Deploy the controller to the cluster with image specified by `IMG`:

```
make deploy IMG=<some-registry>/<project-name>:tag
```