# Docker – Advanced

Docker Advanced covers real-world container usage including storage, networking, multi-container setups, optimization, and image management.

These concepts are essential for production-ready systems.

---

## Docker Volumes (Persistent Storage)

Containers are temporary. If a container is deleted, its internal data is lost.

Volumes are used to persist data.

Create volume:

docker volume create my-volume

Run container with volume:

docker run -v my-volume:/app/data image-name

Volumes are especially important for databases.

---

## Bind Mounts

Bind mounts connect a host directory to a container.

docker run -v /host/path:/container/path image-name

Used mainly in development to sync code between host and container.

---

## Docker Networking

Docker provides multiple network drivers:

bridge – Default isolated network  
host – Shares host network  
none – No networking  

List networks:

docker network ls

Create network:

docker network create my-network

Run container on custom network:

docker run --network my-network image-name

Networking is critical for multi-container communication.

---

## Docker Logs & Debugging

View logs:

docker logs container-id

Follow logs in real-time:

docker logs -f container-id

Inspect container details:

docker inspect container-id

Used for troubleshooting production issues.

---

## Multi-Stage Builds

Used to reduce image size and improve security.

Example:

FROM node:18 AS build
WORKDIR /app
COPY . .
RUN npm install

FROM node:18-slim
WORKDIR /app
COPY --from=build /app /app
CMD ["npm", "start"]

Multi-stage builds help remove unnecessary build dependencies.

---

## Docker Compose

Docker Compose is used to manage multi-container applications.

Instead of running multiple docker run commands, we define services in a docker-compose.yml file.

---

## Complete docker-compose.yml Example

Example: Node.js app with MySQL database

version: "3.8"

services:

  app:
    build: .
    container_name: node_app
    ports:
      - "3000:3000"
    depends_on:
      - db
    environment:
      DB_HOST: db
      DB_USER: root
      DB_PASSWORD: password
      DB_NAME: mydb
    networks:
      - app-network

  db:
    image: mysql:8
    container_name: mysql_db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: mydb
    volumes:
      - db-data:/var/lib/mysql
    ports:
      - "3306:3306"
    networks:
      - app-network

volumes:
  db-data:

networks:
  app-network:

---

### Explanation

app:
- Builds Node.js application
- Exposes port 3000
- Connects to database service
- Uses environment variables

db:
- Uses official MySQL image
- Persists data using volumes
- Connected to same custom network

volumes:
- Ensures database data remains even if container stops

networks:
- Allows containers to communicate securely

---

## Running Docker Compose

Start services:

docker-compose up

Run in detached mode:

docker-compose up -d

Stop services:

docker-compose down

Remove volumes:

docker-compose down -v

---

## Docker Hub

Docker Hub is a public image registry.

It allows:

- Pulling official images
- Sharing custom images
- Version control of images

Login to Docker Hub:

docker login

Tag image:

docker tag image-name username/image-name:tag

Push image:

docker push username/image-name:tag

Pull image:

docker pull username/image-name:tag

Docker Hub is essential for CI/CD pipelines and production deployments.

---

## Image Optimization Best Practices

- Use lightweight base images (alpine, slim)
- Minimize number of layers
- Use .dockerignore
- Avoid storing secrets inside images
- Remove unnecessary files

---

## Docker Security Best Practices

- Do not run containers as root
- Keep images updated
- Scan images for vulnerabilities
- Use environment variables for sensitive data
- Limit exposed ports

---

## Docker in DevOps

Docker plays a central role in DevOps:

- Enables consistent environments
- Used in CI/CD pipelines
- Supports microservices architecture
- Works with Kubernetes for orchestration
- Improves deployment speed and reliability

Strong Docker knowledge is essential for modern DevOps engineers.
