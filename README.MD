# SIT737 - Task 6.1P: Deploying Dockerized Microservice to Kubernetes

This project demonstrates deploying a simple Node.js-based video streaming microservice using Docker and Kubernetes.

 Project Structure
├── Dockerfile-prod # Production-ready Dockerfile ├── src/ │ └── index.js # Node.js entrypoint ├── scripts/ │ └── deploy.yaml # Kubernetes deployment and service YAML ├── package.json ├── README.md #


Steps to Run

1.  Build Docker Image

Make sure you're in the project root directory, then run:

```bash
docker build -t turtle:1 -f Dockerfile-prod .

Test Docker Image Locally (optional)

docker run -p 4000:4000 turtle:1

3. Deploy to Kubernetes
Ensure your Kubernetes cluster is running (e.g., via Docker Desktop), then run:

kubectl apply -f scripts/deploy.yaml
Check resources:

kubectl get pods
kubectl get deployments
kubectl get services
4. Access the Service
Find the NodePort (default is 30000 from deploy.yaml):

kubectl get services
Then in your browser or terminal, access:

http://localhost:30000/video

 Deployment YAML Overview

deploy.yaml includes:

A Deployment named turtle
A Service of type NodePort exposing port 30000
Target container port: 4000
Ensure your app is listening on the correct port and has an active route for /video.

Author 

Sushma Singh
223743838