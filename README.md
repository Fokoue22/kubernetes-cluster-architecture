# KUBERNETES-On-AWS
This is my main kubernetes project repo

## Component that made up the Kubernetes
Kubernetes (K8s) - is an open-source system for automating deployment, scaling and management of containerized
applications. (managing containers at scale N)

When you deploy Kubernetes, you get a cluster.

Kubernetes cluster is a group of one or more worker node consists of a set of worker machines, called nodes,that run containerized application.

Worker node(s) host the PODS (containerized app). They are just Server i.e EC2 server 

Control Plane (Master) manages the worker nodes and the pods in the cluster.

# KUBERNETES ARCHITECTURE  

![Alt text](<kubernetes architecture.png>)


## CONTROL PLANE(MASTER)
This is the brain of kubernetes. He's responsible of sCheduling containers on the worker node. He's the guy that give direction (`ORCHESTRATION`) to each worker node. 

`ON THE MASTER WE HAVE`
1. API SERVER : It's that component in the control plane that allow or manages the comminication between the worker node and the control plane 

2. ETCD (DISTRIBUTED STORAGE): As the is a communication between the Master and the Worker node there are some information that are send between them and need to be store. 
ETCD is just where the contole store all information about the cluster. 

This storage is a `key value storage`. It's a Json file. 

3. SCHEDULER: It's just that component that allow the Master to know exactly where to schedule a container. He is responsible of assigning a conatiner to a node. 

  * when a worker node died, K8s will create a new one. And that new worker node doesn't conatian any POPs on it. So, the Scheduler will schedule some pops/conatiners to the new worker node. 

4. REPLICATION CONTROLLER: This is the `AUTO-SCALLING FOR KUBERNETS`. The contol plane will know how to duplicate a container by using a repliacation controller. 

  * All it does is SCALLING `UP` and `DOWN OF CONATAINERS`