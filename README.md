# Python Web App – CI/CD Pipeline

## Overview
This project is a Python Flask web application with a complete CI/CD pipeline implemented using GitHub Actions and Docker.  
The pipeline automates testing, artifact storage, Docker image creation, and release management following Git best practices.

---

## Tech Stack
- Python (Flask)
- GitHub Actions
- Docker
- GitHub Container Registry (GHCR)

---

## Branching Strategy
- **develop**
  - Continuous Integration (CI)
  - Automated tests
  - Test artifacts upload
- **main**
  - Continuous Integration (CI)
  - Docker image build
  - Docker image publish to GHCR

Direct commits to `main` are not allowed. All changes are merged via Pull Requests.

---

## CI/CD Pipeline Flow

### 1. Push to `develop`
- Install dependencies
- Run automated tests using `pytest`
- Generate test reports
- Upload test reports as GitHub Actions artifacts

### 2. Merge `develop` → `main`
- Re-run tests
- Build Docker image
- Push Docker image to GitHub Container Registry

---

## Docker Image

The Docker image is built only from the `main` branch and stored in GitHub Container Registry.

Pull the image using:
```bash
docker pull ghcr.io/lukha96/phyton-web-app/app:latest

