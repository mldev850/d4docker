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
  -  Replicase count:3 total pods: 4 while running ## kubectl get rc --watch.
  -  Replicaset will remove the pod and set it to the actual replica count i.e 3.
  -  what's the Problem ? sole-nginx and two other replicaset pods.
  -  A bit messy regarding pods mangament.

