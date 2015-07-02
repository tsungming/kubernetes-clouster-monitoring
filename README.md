# kubernetes-clouster-monitoring
Turnkey **[Kubernetes](https://github.com/GoogleCloudPlatform/kubernetes)**
cluster setup with **[Vagrant](https://www.vagrantup.com)** (1.7.2+) and
**[CoreOS](https://coreos.com)**.

Reference:

**[pires/kubernetes-vagrant-coreos-cluster](https://github.com/pires/kubernetes-vagrant-coreos-cluster)**

**[kubernetes/cluster/addons](https://github.com/GoogleCloudPlatform/kubernetes/tree/master/cluster/addons)**


### Step1. Deploy Kubernetes 

```
vagrant up --provider=virtualbox
source ~/.bash_profile
```
  The kubectl command:
  
kubectl get: Display one or many resources. Possible resources include pods (po), replication controllers (rc), services(svc), nodes, events (ev), component statuses (cs), limit ranges (limits),nodes (no), persistent volumes (pv), persistent volume claims (pvc) or resource quotas (quota).

kubectl logs:Print the logs for a container in a pod. If the pod has only one container, the container name is optional.

kubectl describe: Show details of a specific resource.This command joins many API calls together to form a detailed description of a given resource.

```
kubectl get pods
kubectl get pods/(NAME) -o yaml
kubectl describe pods/(NAME)
kubectl logs POD_NSME CONTAINER (ex kubectl logs kube-dns-c806v etcd)

```

### Step2. Deploy cluster-monitoring

```
kubectl create -f addons/cluster-monitoring/influxdb/
```

## Licensing

This work is [open source](http://opensource.org/osd), and is licensed under the [Apache License, Version 2.0](http://opensource.org/licenses/Apache-2.0).
