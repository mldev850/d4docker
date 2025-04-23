### Pods
- Smallest and simplest unit that you create to run containers.

### kubectl
 - CLI utility to interact with the Kubernetes cluster.
 - kubectl translates the command into api instructions 

### Hands-on
- kubectl version
- kubectl config current-context ( Output will be the cluster, kubectl is taking to )
- kubectl config set-context minikube ( Now the context will be updated to minikube )
- kubectl run nginx --image=nginx 
- kubectl get pods
- kubectl describe <RESOURCE> <NAME>        ( To get more information about a Resource )
- kubectl logs nginx                        ( To get logs of the pod )
- kubectl logs nginx --container=nginx      ( To get logs of pod containing more than one containers)
- kubectl delete <RESOURCE> <NAME>

### Exposing Pods via Services
- kubectl expose <RESOURCE> <NAME> --type=NodePort --port=80 ( To expose a service of type Nodeport )
- kubectl get service ( To check service 

### Hands-on Color API
- kubectl run color-api --image=lmacadmey/color-api:1.0.0
- kubectl delete pod --force=true alpine ( Not recommended in Production )

### Object Management
- Refer to Objects repo
  
