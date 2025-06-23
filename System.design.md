# System Design – Moonride DevOps Pipeline

## Overview

Moonride uses modern DevOps practices to ensure reliable, fast, and secure deployments across a Kubernetes-based architecture. CI/CD is fully automated with GitHub Actions.

---

## CI/CD Flow

1. Developer pushes to `main`
2. GitHub Actions:
   - Checks out code
   - Builds Docker image
   - Scans image using Trivy
   - Pushes to DockerHub
   - Deploys to Kubernetes using `kubectl set image`

---

## Kubernetes Components

- `deployment.yaml`: Container versioned services (v1, v1-1, v2)
- `service.yaml`: ClusterIP services for internal routing
- `ingress.yaml`: Exposes API to the world
- `hpa.yaml`: Auto scales pods based on CPU thresholds

---

## Security

- Secrets stored in GitHub Secrets
- DockerHub credentials never stored in plain text
- Trivy scan prevents vulnerabilities from reaching prod
