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

Component,Description,Command Used
Image,A read-only template with instructions for creating a Docker container. It's built from a Dockerfile.,docker build
Container,A runnable instance of a Docker image. It's the isolated environment where the application executes.,docker run
Dockerfile,A text file containing all the commands a user could call on the command line to assemble an image.,N/A (Used by docker build)
Registry,"A central repository for storing and sharing Docker images (e.g., Docker Hub, AWS ECR).",docker push/docker pull

## 🧱 Docker Installation (Linux/Ubuntu)

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
sudo systemctl status docker
```

