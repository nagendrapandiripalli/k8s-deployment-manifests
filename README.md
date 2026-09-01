# Kubernetes Deployment Manifests

Kubernetes manifests for deploying, exposing, and scaling a containerized application with high availability.

## What this does
- Deploys a containerized application with multiple replicas
- Exposes the application via a Kubernetes Service
- Manages external access through an Ingress resource
- Supports rolling updates with zero downtime

## Structure

    k8s-deployment-manifests/
    ├── deployment.yaml   # Defines the app deployment, replicas, and rolling update strategy
    ├── service.yaml      # Exposes the deployment internally within the cluster
    ├── ingress.yaml       # Routes external traffic to the service
    └── README.md

## Usage
Apply the manifests to your cluster:
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
```

Check rollout status:
```bash
kubectl rollout status deployment/myapp-deployment
```

## What it configures
- Rolling update strategy for zero-downtime deployments
- Resource requests/limits for stable scheduling
- Health checks (liveness and readiness probes)
- Horizontal scaling support via replica count

## Tech
- Kubernetes
- YAML
- kubectl

## About
Built to demonstrate container orchestration practices used in production environments — managing rolling updates, cluster health, and both vertical and horizontal scaling for high availability.