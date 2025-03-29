# Flask Kubernetes Deployment Project

![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

A complete example of containerizing a Flask app and deploying it to Kubernetes (Minikube), demonstrating core DevOps principles.

## 🛠️ **Core Technologies Used**
| Component       | Purpose                          | Key Feature Demonstrated              |
|-----------------|----------------------------------|---------------------------------------|
| **Flask**       | Web application framework        | REST endpoint implementation          |
| **Docker**      | Containerization                | Multi-stage builds for production     |
| **Kubernetes**  | Orchestration                   | Deployments, Services, Kustomize     |
| **Minikube**    | Local K8s cluster               | Developer environment simulation      |
| **GitHub Actions** | CI/CD Pipeline               | Automated validation                 |


## 🚀 Quick Start

### Prerequisites
- [Docker](https://docs.docker.com/get-docker/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)

### Local Deployment
```bash
# Start Minikube
minikube start --driver=docker

# Build
minikube docker-env | Invoke-Expression
docker build -t flask-app .

# Deploy
kubectl apply -k k8s/overlays/dev

# Access the app
minikube service flask-app-service
```

## 🔧 Key Components
### Kubernetes Manifests
**Deployment:** Pod specifications and scaling

**Service:** NodePort exposure

**Kustomize:** Environment overlays

## CI/CD Pipeline
**Validates:**
-Docker build
-Kubernetes manifest structure
-Kustomize generation

## 🧠 Learning Highlights

-Debugged ErrImageNeverPull by rebuilding in Minikube Docker

-Configured zero-downtime deployments

-Implemented Kustomize for environment management

## 🚧 Debugging Cheat Sheet
1. Image not found? → Rebuild in Minikube Docker
2. Port conflicts? → Check service.yaml targetPort
3. Pod crashing? → kubectl logs <pod-name>
