# Docker – Basics

Docker is a containerization platform that allows applications to run in isolated environments called containers.

It ensures consistency across development, testing, and production environments.

---

## What is Docker?

Docker allows packaging an application along with its dependencies into a container.

This solves the problem:

"It works on my machine but not in production."

---

## Key Concepts

### Image
Blueprint used to create containers.

### Container
Running instance of an image.

### Dockerfile
File containing instructions to build a Docker image.

### Docker Hub
Public registry to store and share Docker images.

---

## Why Docker is Important in DevOps

- Consistent environments
- Faster deployments
- Lightweight virtualization
- Works well with CI/CD
- Foundation for Kubernetes

---

## Installing Docker (Ubuntu)

sudo apt update  
sudo apt install docker.io  

Check version:

docker --version

---

## Basic Docker Commands

### Pull Image

docker pull nginx

### Run Container

docker run nginx

Run in detached mode:

docker run -d nginx

---

## Port Mapping

Expose container port:

docker run -p 3000:3000 image-name

Left side → Host port  
Right side → Container port

---

## List Containers

docker ps  
docker ps -a  

---

## Stop Container

docker stop container-id

---

## Remove Container

docker rm container-id

---

## Remove Image

docker rmi image-name

---

## Building Your Own Image

Create Dockerfile:

FROM node:18  
WORKDIR /app  
COPY . .  
RUN npm install  
EXPOSE 3000  
CMD ["npm", "start"]

Build image:

docker build -t my-app .

Run container:

docker run -p 3000:3000 my-app

---

## Docker Layers

Each instruction in Dockerfile creates a layer.

Efficient layer usage improves build performance.

---

## Why Docker Basics Matter

- Required for modern deployments
- Used in microservices architecture
- Essential for CI/CD pipelines
- Foundation for Kubernetes

Docker is a must-know tool for DevOps Engineers.
