### Generating Kubernetes Manifests files with Kubectl

- kubectl run nginx-pod --image=nginx:1.27.0 --dry-run=client -o yaml 
- kubectl expose pod nginx-pod --type=NodePort --port=80 --dry-run=client -o yaml


### ShortComings of Imperative Commands with Configuration Files

 - kubectl create -f nginx-pod.yaml
 - Then change the image to nginx:1.2.0-alpine 
 - kubectl replace -f nginx-pod.yaml
  U will get error because under the hood the configuration file u have written and kubectl get pod nginx-pod -o yaml both are different 

 - Tip: kubectl delete -f nginx-pod.yaml -f nginx-svc.yaml ( This will only delete Pods not yaml file )

### Declarative Object Management

 - kubectl apply -f object-management  ( Now whatever yaml files present in object-management will create objects )
 - kubectl diff -f object-management  ( To check differences in Yaml files )
 - kubectl describe pod nginx-pod ( u will see last configured line )

### Migrating from Imperative to Declarative Object Management

  - kubectl create -f nginx-pod.yaml
  - kubectl get pods -o yaml
  - kubectl apply -f nginx-pod.yaml 

### Multiple Kubernetes Manifests

  - Approach 1: Yaml file ( --- )
  - Approach 2: All objects file related to a task in same folder
Best Approach depends on the Usecase.

  
