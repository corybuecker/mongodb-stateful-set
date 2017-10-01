# MongoDB as Stateful Set with Replication

**Please note that I do not maintain this any longer. I recommend [using the official Helm chart](https://github.com/kubernetes/charts/tree/master/stable/mongodb-replicaset).**

Kubernetes Version: 1.5.2

MongoDB Version: 3.2.4

The default configuration only provisions 5GB for the /data/db directory. The configuration also assumes that you are using some form of [dynamically-provisioned storage class](https://kubernetes.io/docs/user-guide/persistent-volumes/#provisioner) for the volumes. Feel free to change the provisioned size or type to another storage volume. You can also remove the volume mount and use the underlying host's storage.

You can also tune the number of replicas by adjusting the replicas setting in mongodb.yml. The default is to provision two instances.

## Getting Started

    kubectl apply -f mongodb.yml -f service.yml

## Metrics

If you are running Prometheus and would like to collect metrics from the Mongo instances.

    kubectl apply -f metrics/mongodb.yml

## Links

* The awesome [MongoDB "sidecar" container](https://github.com/cvallance/mongo-k8s-sidecar) by [cvallance](https://github.com/cvallance).
