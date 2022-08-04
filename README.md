## Main Features

- Multi-Host Container Scheduling
- Scalability
- Availability
- Registration
- Discovery
- Persistent Storage
- Application Upgrades and Downgrades
- Logging and Monitoring
- Secrets Management

https://www.cncf.io/
https://kubernetes.io/
  
### KubeCon
### CloudNativeCon

## Other Implementations

- Nomad
- Rancher
- Docker Swarm
- Mesos
- AWS ECS / EKS
- Google Anthos

## Serverless

- Consider serverless technologies if:
  - Strating to build your infrastructure from scratch
  - Running your infrastructure in the cloud

## Architecture

- Master Node
  - API Server
    - etcd
    - kubectl
      - kubeconfig
  - Scheduler
  - Controller Manager
- Worker Node
  - kubelet
  - kube-proxy
  - Docker
    - Pods
      - containers

## Ways to run Kubernetes

- Minikube (https://minikube.sigs.k8s.io/docs/)
- Docker Desktop
- Kubernetes in Docker (kind)
- Managed Kubernetes service in a cloud
  - Amazon Elastic Kubernetes Service (EKS)


## Commands

minikube start

minikube status

minikube stop


kubectl get nodes

kubectl get all

kubectl create -f helloworld.yaml

kubectl expose deployment helloworld --type=NodePort

minikube service helloworld

kubectl get deployment

kubectl get deployment/helloworld -o yaml


kubectl get service

kubectl get service/helloworld -o yaml

### Labels

kubectl get pods --show-labels

kubectl label pod/helloworld app=helloworld

kubectl label pod/helloworld app-

kubectl get pods

kubectl get pods --selector env=production

kubectl get pods --selector dev-lead=karthik,env=staging

kubectl get pods -l dev-lead=karthik,env=staging

kubectl get pods -l dev-lead!=karthik,env=staging --show-labels

kubectl get pods -l 'release-version in (1.0,2.0)'

kubectl get pods -l 'release-version in (1.0,2.0)' --show-labels

kubectl get pods -l 'release-version notin (1.0,2.0)'

kubectl get pods -l 'release-version notin (1.0,2.0)' --show-labels

kubectl delete pods -l dev-lead=karthik