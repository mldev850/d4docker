### ReplicaSets
 - Ensure that a certain number of pods is running at any given time.
 - ReplicaSets work by identifying pods via selectors.
 - If number of pods are lesser, so it based on template it will create pods.

### Creating and Managing Replicasets
 - kubectl get rs
 - check rs.yaml file

### Shortcomings of Replicaset - Updating Pods
  - Changing image in yaml file will not reflect in pods.
  - kubectl get pods --watch

### Shortcomings of Replicaset - Manage Existing Pods
  -  
