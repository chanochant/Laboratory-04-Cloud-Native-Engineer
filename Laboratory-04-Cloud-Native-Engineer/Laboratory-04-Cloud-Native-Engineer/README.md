# Laboratory 04 — The Cloud-Native Engineer

## Mission Overview

This laboratory activity focuses on cloud-native engineering, containerization, and Docker. The activity compares traditional Virtual Machines (VMs) with containers and demonstrates how Docker can be used to deploy a web application efficiently. Using the KillerCoda Docker environment, an Nginx web server is pulled, deployed, tested, managed, and removed using Docker CLI commands.

## Objectives

At the end of this laboratory activity, I should be able to:

- Differentiate between traditional Virtual Machines and containers.
- Access a Docker-enabled cloud environment using KillerCoda.
- Execute fundamental Docker CLI commands.
- Pull, run, and manage a containerized Nginx web server.
- Map a host port to a container port.
- Verify a web server using a local HTTP request.
- Manage the lifecycle of a Docker container.
- Create technical documentation using Markdown.
- Maintain an organized GitHub Cloud Computing Portfolio.

## Docker Commands Executed

### Checkpoint 3 — Docker Verification

```bash
docker --version
docker info
sudo systemctl status docker
```

### Checkpoint 4 — Nginx Deployment

```bash
docker pull nginx
docker run -d --name nginx-server -p 8080:80 nginx
docker ps
curl http://localhost:8080
```

### Checkpoint 5 — Container Lifecycle

```bash
docker ps
docker stop nginx-server
docker ps
docker ps -a
docker rm nginx-server
docker ps -a
```

## Skills Learned

I learned how to compare Virtual Machines and containers, verify a Docker environment, pull images from Docker Hub, run containers in detached mode, map ports, and test a web server from the terminal. I also learned how to stop, inspect, and remove containers and how to document technical procedures using Markdown. The activity strengthened my command-line, troubleshooting, documentation, and GitHub portfolio management skills.

## Challenges Encountered

One challenge was becoming familiar with the Docker CLI and understanding the difference between an image and a container. Another challenge was understanding port mapping and how port 8080 on the host connects to port 80 inside the Nginx container. I also had to carefully follow the container lifecycle so that the container was stopped before it was removed. Checking the terminal output after each command helped me verify that the operations were successful.

## Evidence

### Docker Environment

Add your actual screenshot here:

![Docker Version](screenshots/docker-version.png)

### Nginx Running

Add your actual screenshot here:

![Nginx Running](screenshots/nginx-running.png)

### Container Lifecycle

Add your actual screenshot here:

![Container Lifecycle](screenshots/container-lifecycle.png)

## Repository Structure

```text
Laboratory-04-Cloud-Native-Engineer/
├── README.md
├── virtualization-vs-containers.md
├── docker-deployment.md
├── reflection.md
└── screenshots/
    ├── docker-version.png
    ├── nginx-running.png
    └── container-lifecycle.png
```
