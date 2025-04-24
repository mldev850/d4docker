### Deployments

- Manage and update applications at scale.
- Deployment Offers a Higher level of Abstraction on top of ReplicaSets

### Additional Features
- Rolling Updates
- Roll backs
- Declarative updates
- History and revision control
- Advanced rollouts

### Creating and Managing Deployments
- If we don't mention strategy: rolling updates by default rolling updates will be used.
- nginx-deployment → Deployment (abstracts the desired state)
- nginx-deployment-6d8469f8db → ReplicaSet (created by Deployment, abstracts the Pod template)
- nginx-deployment-6d8469f8db-zmhhg → Pod (individual unit running your container).
- pod-template-hash : Will change if content is changed.

### Updating Pod Template
 - change image and each and every pod will have image changes

### Understanding Rollouts
 - kubectl rollout --help
 - kubectl rollout history deployment/nginx-deployment
 - kubectl rollout undo deployment/nginx-deployment ( One Previous step Back )
 - kubectl rollout history deployment/nginx-deployment --revision=2  -o  yaml
 
 
