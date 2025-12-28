# Python Web App – CI/CD Pipeline

## Overview
A Python Flask web application with a full CI/CD pipeline using GitHub Actions and Docker.

## Tech Stack
- Python (Flask)
- GitHub Actions
- Docker
- GitHub Container Registry

## Branching Strategy
- `develop`: CI (tests, artifacts)
- `main`: CI + Docker image build & push

## CI/CD Flow
1. Push to `develop`
   - Run tests
   - Upload test artifacts
2. Merge `develop` → `main`
   - Run tests
   - Build Docker image
   - Push image to GHCR

## Docker Image
```bash
docker pull ghcr.io/lukha96/phyton-web-app/app:latest

