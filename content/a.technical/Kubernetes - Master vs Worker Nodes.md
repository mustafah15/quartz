---
tags:
  - kubernetes
  - infrastructure
related: "[[kubernetes]]"
type: permanent
---
## Kubernetes Master Node
the master is another node with Kubernetes installed on it and it's configured as a master, the master watches over the other nodes in the cluster and is responsible for the actual orchestration of containers on the worker nodes.

#### Master Node owns the following components 
- kube-apiserver
- etcd
- controller 
- schedular

#### Worker Node owns the following components 
- kubelet
- container run time



