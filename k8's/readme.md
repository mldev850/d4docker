### Kubernetes
- Managing Containers at Scale.
### Kubernetes ARCHITECTURE
- Control Plane : Brain of Kubernetes Cluster
- Data Plane: Containers runs here
### Control Plane components
 - API server : Entrypoint to interact with the k8's cluster
 - Scheduler: Schedules pod to respective node based on constraints
 - Etcd: Distributed-key value store contains all the cluster information except application (containerised Applctn) info.
 - Controller Manager: Used to manage running controller processes like replica set controller etc.
 - Cloud COntroller Manager: Integration with cloud infrastructure
### Data Plane Components
- Kubelet: Runs on each worker node and interacts with control plane
- container run time: Responsible for running containers
- kubeproxy : Responsible for managing network related as well as routing request to appropriate services


