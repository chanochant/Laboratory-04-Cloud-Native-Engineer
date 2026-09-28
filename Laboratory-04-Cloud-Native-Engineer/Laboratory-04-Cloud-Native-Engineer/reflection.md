# Mission 4 Reflection

This laboratory activity helped me understand how containerization differs from traditional Virtual Machine virtualization and why containers are useful in cloud-native environments. A Virtual Machine normally requires a complete guest operating system to boot, which can take more time and consume more memory and storage. In comparison, a Docker container shares the host operating system kernel and starts the application without needing to boot another complete operating system. Because of this, containers can provide a faster and more lightweight setup process for many applications.

Port mapping is necessary because a web server inside a container is running in an isolated container network environment. In this activity, the `-p 8080:80` option connects port 8080 on the host to port 80 inside the Nginx container. Nginx normally listens on port 80, so the mapping allows a request sent to `http://localhost:8080` on the host to reach the Nginx service inside the container.

When `docker rm` is used, the specified container is removed from Docker. Data stored only in the container's writable layer can be lost because that storage belongs to the container. However, data stored in persistent Docker volumes or external storage can remain available even after the container is removed. This demonstrates why persistent storage is important for applications that need to preserve data.

Containerization can also improve collaboration between software developers and IT operations teams. Developers can package an application and its dependencies into a container image, while operations teams can deploy that same image in different environments. This supports DevOps by making development, testing, and deployment more consistent.

My GitHub portfolio is evolving from a collection of projects into a more organized record of my technical learning. This laboratory adds Docker, containerization, Linux command-line operations, technical documentation, and troubleshooting to the skills demonstrated in my portfolio.
