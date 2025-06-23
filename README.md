# Moonride – DevOps Deployment 🚀

A containerized microservice architecture with CI/CD built using Docker, Kubernetes, and GitHub Actions. Designed for scalable e-commerce APIs with automated deployment and security in mind.

## 🛠️ Stack
- Docker + DockerHub
- Kubernetes (Minikube or Cloud)
- GitHub Actions
- Trivy Security Scanner
- Horizontal Pod Autoscaler, Ingress NGINX

## 🚀 Quick Start

```bash
# Clone & navigate
git clone https://github.com/Codebruh-sudo/moonride.git
cd moonride

# Build & run locally
docker build -t moonride .
docker run -p 5000:5000 moonride


## CI/CD ( for security reasons)
- name: Scan Docker image with Trivy
  uses: aquasecurity/trivy-action@master
  with:
    image-ref: '${{ secrets.DOCKER_USERNAME }}/moonride:latest'



---

### 📓 `CHANGELOG.md`

```markdown
# Changelog

## [1.2.0] – 2025-06-23
### Added
- Trivy scanning to GitHub Actions workflow
- Complete DevOps documentation
- Ingress endpoint documentation in README

## [1.1.0] – 2025-06-22
### Changed
- Refactored deployment into `k8s/` folder
- Added HPA to Kubernetes configs

## [1.0.0] – 2025-06-21
### Added
- Initial CI/CD pipeline
- Dockerfile, GitHub Actions, deployment configs

