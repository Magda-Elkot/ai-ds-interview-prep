## 1. What is Docker?

Docker is a tool that lets you package your **code, dependencies, and environment** into one box (called a **container**) so it can run the same way anywhere.

---

## 2. Why Docker?

### Without Docker  
- You write an AI model on your laptop (Python 3.10, PyTorch 2.1, CUDA drivers, etc.).  
- When you try to run it on a server or a teammate’s computer, something breaks.  
 *“works on my machine 😅”* problem.  

### With Docker  
- You put your whole setup into a container.  
- Now anyone can run it — server, cloud, or laptop — without worrying about missing libraries or different versions.  

---

## 3. Core Concepts

### a. Image  
- A **blueprint (recipe)** of everything your app needs: Python version, libraries, files, and configs.  
- Example: *“Start with Ubuntu, install Python 3.10, add PyTorch, copy my code.”*  

### b. Container  
- A **running instance** of an image.  
- Like making a sandwich from a recipe — you can run many containers from the same image.  

### c. Dockerfile  
- A **text file** where you write instructions to build your image.  

Example:

```dockerfile
FROM python:3.10
RUN pip install torch torchvision
COPY . /app
CMD ["python", "train.py"]

```

## 4. Docker Hub

Like GitHub, but for Docker images.  

You can push your own images or download ready-made ones (e.g., `pytorch/pytorch`).  

---

## 5. Why AI Engineers Care About Docker

- **Consistency** → ML model runs the same on local, cloud, or teammate’s laptop.  
- **Reproducibility** → Anyone can reproduce experiments exactly.  
- **Deployment** → Easy to ship models to servers or Kubernetes clusters.  
- **Portability** → Works on Linux, Windows, and macOS seamlessly.  

---

## 6. In Short

Docker is like a **magic box** that guarantees your AI code will run anywhere, exactly the same way.  

---

# Potential Interview Questions & Answers

### 1. Explain the core components of Docker: the Dockerfile, Image, and Container. How do they relate to each other?  

- **Dockerfile** → recipe with instructions.  
- **Image** → packaged result of that recipe.  
- **Container** → running instance of an image.  

 Analogy: *Dockerfile = recipe, Image = packaged meal, Container = meal being served.*  

---

### 2. Describe a scenario where using Docker would be beneficial for a data science or machine learning project.  

- Developing an ML model with specific Python and library versions.  
- A teammate with different versions gets dependency conflicts.  
- With Docker, you share the image → everyone runs the same environment → guaranteed reproducibility.  

---

### 3. What is the difference between `docker run` and `docker start`?  

- `docker run` → creates a new container from an image and starts it (first launch).  
- `docker start` → restarts an existing, stopped container.  

---

### 4. How would you handle persistent data in a Docker container? What is a Docker volume, and why is it useful?  

- Containers are **ephemeral** — data is lost when removed.  
- Use **volumes** to persist data.  
- Volumes mount a host directory (or dedicated storage) into the container → keeps data like DB files or checkpoints safe even if the container stops.  

---

### 5. What is Docker Compose, and when would you use it?  

- A tool to define and run **multi-container applications** with a YAML file.  
- Example: web app + database + cache.  
- Command: `docker-compose up` starts all services.  
- Useful for managing complex apps with multiple interconnected containers.  

---

### 6. Explain a multi-stage Docker build and its benefits.  

- Uses **multiple FROM statements** in a single Dockerfile.  
- Example:  
  - Stage 1 = build with compilers/tools.  
  - Stage 2 = copy only the output into a minimal runtime image.  
- **Benefits:**  
  - Smaller final image.  
  - More secure (no build tools in runtime).  
  - Faster deployments.  

---

# Common Docker Commands (Cheatsheet)

```bash
# Build an image
docker build -t myapp .

# Run a container
docker run -it myapp

# List running containers
docker ps

# List all containers (including stopped)
docker ps -a

# Stop a container
docker stop <container_id>

# Remove a container
docker rm <container_id>

# Remove an image
docker rmi <image_id>

# Run with port mapping
docker run -p 8080:80 myapp

# Run with volume (persistent data)
docker run -v /host/path:/container/path myapp
