
# Kustomize HandsOn

This repository demonstrates the use of **Kustomize** for managing Kubernetes configurations across different environments (e.g., staging and production). Each example folder in this repository contains a Kustomize-based setup with specific tasks related to Kubernetes resource management.

### Prerequisites

- A running Kubernetes cluster.
- `kubectl` installed (version 1.14 or higher, which includes Kustomize).
- Basic understanding of Kubernetes concepts like Pods, ConfigMaps, Namespaces, etc.

### Example 1: Managing Staging and Production Environments

#### Commands

    kubectl create namespace staging
    kubectl apply -k environments/staging
____________________
    
    kubectl apply -k environments/production
    kubectl get pods -n production
    kubectl delete -k environments/production

    
### Example 2: Kustomize configMapGenerator

#### Commands

    kubectl apply -k staging
    kubectl get pods
    kubectl get cm
    kubectl get cm config-<id> -o yaml
    kubectl exec nginx-deployment-<id> -- cat /etc/config/credentials

### Example 3: Kustomize secret generator
#### Commands

    kubectl apply -k production
    kubectl get pods
    kubectl exec nginx-deployment-<id> -- env

### Example 4: Kustomize image name or tag

#### Commands

    kubectl apply -k staging
    kubectl describe pods

