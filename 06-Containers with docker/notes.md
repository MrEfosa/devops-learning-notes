# 🐳 Docker – DevOps Bootcamp Notes (Module 6)

## 📘 Overview

**Docker** is a **containerization platform** that allows developers and DevOps engineers to package applications and their dependencies into a **single portable unit** called a **container**.

Think of it as:
> “A lightweight virtual machine that only contains what your app needs to run.”

---

## ⚙️ Key Concepts

| Term | Description |
|------|--------------|
| **Image** | A *template* that contains the app code + dependencies. (Like a class in OOP.) |
| **Container** | A *running instance* of an image. (Like an object in OOP.) |
| **Dockerfile** | A script with instructions on how to build an image. |
| **Docker Engine** | The runtime that builds, runs, and manages containers. |
| **Docker Hub** | A public registry for storing and sharing Docker images. |
| **Volume** | A persistent storage mechanism for containers. |
| **Network** | Allows containers to communicate with each other and the host. |

---

## 🧩 Why Docker?

- 🚀 **Consistency:** Same environment across dev, test, and production.
- 💨 **Speed:** Containers start in seconds.
- 💡 **Lightweight:** Uses the host OS kernel — no full OS needed.
- 🔁 **Scalability:** Easily deploy across multiple environments.
- 💰 **Cost-effective:** More containers per host than VMs.

---

## 🐋 Docker Architecture

+---------------------------------------------+
| Docker CLI |
+-----------------------+---------------------+
| Docker Daemon | Docker REST API |
+-----------------------+---------------------+
| Container Runtime (runc) |
+---------------------------------------------+
| Host Operating System |
+---------------------------------------------+


- **Docker CLI:** Command-line interface to interact with Docker.
- **Docker Daemon (`dockerd`):** Background service managing images and containers.
- **Docker Registry:** Stores images (e.g., Docker Hub or private registry).

---


## 🧱 Docker Installation (Linux/Ubuntu)

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
sudo systemctl status docker
```
## 🐳 Docker Containerization Cheat Sheet (Module 7)

| Concept/Command | Description | Syntax/Example |
| :--- | :--- | :--- |
| **Image** | Read-only template for creating containers; built from a `Dockerfile`. | N/A (Build with `docker build`) |
| **Container** | A runnable instance of an image. Isolated and portable. | N/A (Run with `docker run`) |
| **Dockerfile** | Text file with instructions for building a Docker image layer by layer. | See Dockerfile Instructions below. |
| **Registry** | Storehouse for public/private Docker Images (e.g., Docker Hub). | `docker pull/push <image>` |
| **Run** (Create & Start) | Creates a container from an image and runs a command. | `docker run -d -p 8080:80 --name web nginx` |
| **List Running** | Lists all **running** containers. Use `-a` for all (stopped/running). | `docker ps` / `docker ps -a` |
| **Execute** (Shell) | Executes a command inside a **running** container (e.g., starting a shell). | `docker exec -it <id/name> /bin/bash` |
| **Logs** | Retrieves the output (logs) of a container. | `docker logs -f <id/name>` (Follow mode) |
| **Stop/Remove** | Gracefully stops a running container, then removes it permanently. | `docker stop <id/name>` then `docker rm <id/name>` |
| **Build Image** | Creates an image from a `Dockerfile` in the current directory (`.`). | `docker build -t my-app:v1 .` |
| **Port Mapping** | Maps a port on the **Host** machine to a port inside the **Container**. | `-p <HOST_PORT>:<CONTAINER_PORT>` (e.g., `-p 8080:80`) |
| **Volume** | Mechanism to persist container data outside the container's lifecycle. | `-v <volume_name>:<container_path>` |
| **Bind Mount** | Mounts a host directory/file directly into a container (useful for Dev/Config). | `-v /host/path:/container/path` |

---

### 📝 Key Dockerfile Instructions

| Instruction | Purpose | Example |
| :--- | :--- | :--- |
| `FROM` | Sets the base image. | `FROM python:3.9-slim` |
| `WORKDIR` | Sets the default directory for subsequent commands. | `WORKDIR /app` |
| `COPY` | Copies files from the host into the image. | `COPY requirements.txt .` |
| `RUN` | Executes commands during the **build** process (creating a layer). | `RUN pip install -r requirements.txt` |
| `EXPOSE` | Documents the port the application listens on. | `EXPOSE 5000` |
| `CMD` | Defines the command to run when a **container starts** (default executable). | `CMD ["python", "app.py"]` |

