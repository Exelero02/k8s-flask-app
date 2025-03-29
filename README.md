# Flask Kubernetes Deployment Project

![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

A complete example of containerizing a Flask app and deploying it to Kubernetes (Minikube), demonstrating core DevOps principles.

## ✨ Features

- **Containerized Flask application** with Docker
- **Kubernetes manifests** using Kustomize
- **CI/CD Pipeline** with GitHub Actions
- **Local development** setup with Minikube

## 🚀 Quick Start

### Prerequisites
- [Docker](https://docs.docker.com/get-docker/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)

### Local Deployment
```bash
# Start Minikube
minikube start

# Build and deploy
minikube docker-env | Invoke-Expression
docker build -t flask-app .
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
