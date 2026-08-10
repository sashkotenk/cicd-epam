# Lab 1: Continuous Deployment Using GitHub Actions

This repository contains the solution for the EPAM **Continuous Integration and Continuous Delivery Fundamentals** lab on deploying a Node.js application to Minikube with GitHub Actions.

## Stack

- Node.js + Express
- Docker
- Kubernetes
- Minikube
- GitHub Actions

## Application

The application listens on port `3000` and returns:

```text
Hello World
```

for requests to `/`.

## CI/CD workflow

On every push, GitHub Actions:

1. checks out the repository;
2. starts Minikube;
3. verifies the Kubernetes cluster;
4. builds the Docker image inside Minikube's Docker environment;
5. deploys the application with Kubernetes;
6. waits for the Deployment rollout;
7. obtains the Minikube service URL;
8. verifies the deployed application with `curl`.

## Files

- `Dockerfile` — Node.js application image;
- `package.json` — application dependencies and start command;
- `server.js` — Express application;
- `k8s-node-app.yaml` — Kubernetes Deployment and NodePort Service;
- `.github/workflows/deploy-to-minikube-github-actions.yaml` — GitHub Actions workflow.

The workflow is configured to run automatically after each push to the repository.
