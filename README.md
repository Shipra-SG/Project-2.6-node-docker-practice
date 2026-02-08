# Node Docker Practice

This repository contains a **Node.js application** containerized using **Docker** as part of my hands-on DevOps learning.

The goal of this project was to understand:

* How to write a **Dockerfile** for a Node.js application
* How Docker images and containers work
* How to build and run Docker images and containers
* How to host a Node.js web application inside Docker

---

## Project Overview

This is a simple Node.js application that responds with a message when accessed via a web browser or HTTP tool. The focus of this project is to practice Docker fundamentals by:
✔ Writing a Dockerfile
✔ Building a Docker image
✔ Running a container
✔ Exposing ports and verifying app access

---

## Tech Stack Used

| Technology | Purpose               |
| ---------- | --------------------- |
| Node.js    | Application language  |
| Express.js | Web framework         |
| Docker     | Containerization      |
| Git        | Source control        |
| Linux      | Execution environment |

---

## Application Description

In this project:

* The Node.js app (`index.js`) starts a basic web server using Express
* It responds with a message when accessed via public-IP on a specific port
* We learn how to containerize this using Docker

---

## Dockerfile Explained

Here is what each line does:

```dockerfile
FROM node:18-alpine
```
✔ Uses official lightweight Node.js image from Docker Hub.

---

```dockerfile
WORKDIR /app
```
✔ Sets working directory inside the container.
All future commands run relative to `/app`.

---

```dockerfile
COPY package*.json ./
```
✔ Copies dependency configuration files first - helps use Docker cache.

---

```dockerfile
RUN npm install
```
✔ Installs Node.js project dependencies inside the container.

---

```dockerfile
COPY . .
```
✔ Copies the rest of the application code into the container.

---

```dockerfile
EXPOSE 3000
```
✔ Exposes port 3000 to allow access from outside the container.

---

```dockerfile
CMD ["npm","start"]
```
✔ Starts the Node.js application using the start script in **package.json**.

---

## How to Run This Project

### 1. Clone the Repo

```bash
git clone <repo-URL>
cd <project>
```

---

### 2. Build Docker Image

```bash
docker build -t node-docker-app .
```

This creates the Docker image named **node-docker-app**.

---

### 3. Run Docker Container

```bash
docker run -d -p 3000:3000 --name node-container node-docker-app
```

Now open your browser and visit:

```
http://<public-IP>:3000
```
✔ You should see the Node.js app message responding!

---

## Learning Outcomes

By completing this project, I learned:

* How containerization works with Node.js applications
* How to write effective Dockerfiles
* Docker build and run commands
* Exposing ports via Docker containers
* Using lightweight Docker images for faster deployment

---

## Why This Matters

Containerization is a key DevOps skill that:

* Makes applications portable
* Simplifies deployments
* Enables scalable production workflows
* Integrates with Kubernetes & CI/CD pipelines

This project gives foundational knowledge before moving to:
➡ Kubernetes
➡ Cloud deployments (AWS EKS)
➡ CI/CD automation

---

## 👩‍💻 Author

**Shipra**
DevOps & Cloud Enthusiast 🌱
Learning Docker → Kubernetes → AWS

Just ask! 🚀
