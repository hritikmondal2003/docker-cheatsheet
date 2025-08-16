# 🐳 Docker Cheat Sheet – Apna College

A quick reference guide for essential Docker commands.

---

## 📦 IMAGES

| Command | Description |
|---------|-------------|
| `docker images` | List all local images |
| `docker rmi <image_name>` | Delete an image |
| `docker image prune` | Remove unused images |
| `docker build -t <image_name>:<version> .` | Build image from Dockerfile (`version` optional) |
| `docker build -t <image_name>:<version> . --no-cache` | Build without cache |

---

## 🛠️ CONTAINERS

| Command | Description |
|---------|-------------|
| `docker ps -a` | List all containers (running + stopped) |
| `docker ps` | List running containers |
| `docker run <image_name>` | Create and run a new container (pulls from DockerHub if not found locally) |
| `docker run -d <image_name>` | Run container in background (detached mode) |
| `docker run --name <container_name> <image_name>` | Run with custom container name |
| `docker run -p <host_port>:<container_port> <image_name>` | Port binding |
| `docker run -e <var_name>=<value> <image_name>` | Set environment variable |
| `docker start <container_name>` | Start a container |
| `docker stop <container_name>` | Stop a container |
| `docker inspect <container_name>` | Inspect container |
| `docker rm <container_name>` | Delete a container |

---

## 🔍 TROUBLESHOOTING

| Command | Description |
|---------|-------------|
| `docker logs <container_name>` | View logs of container |
| `docker exec -it <container_name> /bin/bash` | Open Bash shell |
| `docker exec -it <container_name> sh` | Open shell (if Bash not available) |

---

## ☁️ DOCKER HUB

| Command | Description |
|---------|-------------|
| `docker pull <image_name>` | Pull image from DockerHub |
| `docker push <username>/<image_name>` | Push image to DockerHub |
| `docker login -u <username>` | Login to DockerHub |
| `docker login` | Alternative login |
| `docker logout` | Logout from DockerHub |
| `docker search <image_name>` | Search for image on DockerHub |

---

## 📂 VOLUMES

| Command | Description |
|---------|-------------|
| `docker volume ls` | List all volumes |
| `docker volume create <volume_name>` | Create new named volume |
| `docker volume rm <volume_name>` | Delete named volume |
| `docker run --volume <volume_name>:<mount_path>` | Mount named volume |
| `docker run --mount type=volume,src=<volume_name>,dest=<mount_path>` | Mount using `--mount` |
| `docker run --volume <mount_path>` | Mount anonymous volume |
| `docker run --volume <host_path>:<container_path>` | Bind mount using `--volume` |
| `docker run --mount type=bind,src=<host_path>,dest=<container_path>` | Bind mount using `--mount` |
| `docker volume prune` | Remove unused (anonymous) volumes |

---

## 🌐 NETWORK

| Command | Description |
|---------|-------------|
| `docker network ls` | List all networks |
| `docker network create <network_name>` | Create a new network |
| `docker network rm <network_name>` | Remove a network |
| `docker network prune` | Remove all unused networks |

---

💡 **Pro Tip:**  
Use `docker system prune` to remove all stopped containers, unused networks, and dangling images in one go.
