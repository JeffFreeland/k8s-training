# Kubernetes Training

Assumptions: 
- General idea for what containers are. We won’t be building them, just deploying them. 
- Know yaml okay or can pick it up. 

For exercise purposes, I made a flask app with a few endpoints which can be used to not have to make your own. 
DockerHub: https://hub.docker.com/repository/docker/jeffreyfreeland/flask-hello-world
Code Repo (with endpoints documented): https://github.com/JeffFreeland/flask-hello-world


## Some notes for the exercises
- Type things out rather than copy/pasting, as this will help it be better retained. 
- Revisit previously completed tasks after you've done the ones that follow. Doing something multiple times helps it stick, especially if a little bit of time has passed. 


## General knowledge
| task|
|--|
| Explain the benefits that k8s provides over running containers without k8s (orchestration, so easy scaling, restarting stopped containers, etc) |
| Create a deployment that runs a single container |
| Use kubectl to get pods |
| Use kubectl to port-forward to a deployment or pod |
| Explain the general architecture of how a k8s cluster works. Pods, deployments, services, replicasets. |
| Create a service for the deployment, and explain how this decouples it from the specific deployment |
| Use kustomize to be able to deploy both the deployment and service with `kubectl -k` |

## config

| task|
|--|
| Add env variables to a deployment |
| Use kubectl describe to inspect the deployment with env variables |
| Add a configmap that contains a different variable to add to the deployment |
| Add a secret, but demonstrate that it’s just a base64 value stored in volatile memory, and not very secure. Foot stop by using base64 to “unencrypt” the value (because it’s not encrypted at all), and stress that secrets *cannot* go in source control just because they’re not immediately visible. |

Good time to mention the 12 factor app. We can do all this config with k8s (and other orchestration options), so if we code with that in mind, we have a lot of control over the application without needing changes to source code. 
