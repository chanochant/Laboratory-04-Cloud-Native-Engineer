# Docker Deployment

## Checkpoint 3 — Enter the Docker Playground

### 1. Verify the Docker Version

```bash
docker --version
```

This command displays the Docker version installed in the KillerCoda environment.

### 2. Check the Docker Environment

```bash
docker info
```

This command displays detailed information about the Docker environment, including the Docker server, containers, images, storage, and configuration.

### 3. Check the Docker Service

```bash
sudo systemctl status docker
```

This command checks the status of the Docker service and confirms whether Docker is running.

> **Evidence:** `screenshots/docker-version.png`

---

# Checkpoint 4 — Deploy Your First Container

## 1. Pull the Official Nginx Image

```bash
docker pull nginx
```

This command downloads the official Nginx image from Docker Hub to the local Docker environment.

## 2. Run the Nginx Container

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

This command creates and starts an Nginx container in detached mode, names it `nginx-server`, and maps host port 8080 to container port 80.

### Port Mapping Explanation

The option:

```text
-p 8080:80
```

means:

```text
Host Port 8080 → Container Port 80
```

Nginx listens on port 80 inside the container, while users can access it through port 8080 on the host.

## 3. Verify the Running Container

```bash
docker ps
```

This command lists currently running containers and allows the Nginx container to be verified.

## 4. Test the Nginx Web Server

```bash
curl http://localhost:8080
```

This command sends an HTTP request to the Nginx web server through port 8080 and displays the HTML returned by Nginx.

A successful response should contain the Nginx welcome page, including text similar to:

```text
Welcome to nginx!
```

> **Evidence:** `screenshots/nginx-running.png`

---

# Checkpoint 5 — Container Lifecycle

## 1. List Running Containers

```bash
docker ps
```

This command displays all Docker containers that are currently running.

## 2. Stop the Running Container

```bash
docker stop nginx-server
```

This command stops the running Nginx container without immediately removing it.

## 3. Verify That It Is Stopped

```bash
docker ps
```

This command confirms that the Nginx container is no longer listed among the running containers.

## 4. View All Containers

```bash
docker ps -a
```

This command displays both running and stopped containers, allowing the stopped Nginx container to be verified.

## 5. Remove the Container Completely

```bash
docker rm nginx-server
```

This command removes the stopped Nginx container from Docker.

## 6. Verify That It Was Removed

```bash
docker ps -a
```

This command verifies that the `nginx-server` container no longer appears among the existing containers.

> **Evidence:** `screenshots/container-lifecycle.png`

## Complete Lifecycle Sequence

```bash
docker ps
docker stop nginx-server
docker ps
docker ps -a
docker rm nginx-server
docker ps -a
```

## What Happens to Container Data?

When `docker rm` removes a container, data stored only inside that container's writable layer is removed with the container. Data that was stored using Docker volumes or another persistent storage mechanism can remain available after the container is removed. Therefore, important application data should be stored using persistent storage rather than relying only on the container's temporary writable layer.
