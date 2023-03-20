## Docker Cheatsheet

### Docker Basics
- `docker version`: Check the version of Docker running on your machine.
- `docker info`: View system-wide information about Docker.
- `docker help`: View a list of Docker commands.

### Docker Images
- `docker images`: List all Docker images on your machine.
- `docker search <image name>`: Search Docker Hub for an image.
- `docker pull <image name>`: Download an image from Docker Hub.
- `docker build -t <tag name> <directory>`: Build a new Docker image from a Dockerfile.

### Docker Containers
- `docker create --name <container-name> -p <host-port>:<container-port> <image>`: creates a Docker container from an image with a specific name and port mapping.
- `docker port <container-name>`: shows the mapping between the container's port and the host machine's port.
- `docker start <container-name>`: Start a stopped Docker container.
- `docker pause <container-name>`: temporarily stops a running Docker container.
- `docker run <image name>`: Create and start a new Docker container.
- `docker ps`: List all running Docker containers.
- `docker stats`: shows the resource usage of all the Docker containers on the local machine.
- `docker logs <container name>`: View the logs of a Docker container.
- `docker stop <container name>`: Stop a running Docker container.
- `docker kill <container-name>`: forcefully stops a running Docker container.
- `docker rm <container name>`: Remove a stopped Docker container.
- `docker rmi <image>`: removes a Docker image from the local machine.
- `docker exec <container-name> <command>`: runs a command inside a running Docker container.
- `docker commit <container-name> <new-image-name>`: creates a new Docker image from a running Docker container.
- `docker save <image> -o <filename.tar>`: saves a Docker image to a tar file.
- `docker login`: logs into Docker Hub.
- `docker push <image>`: pushes a Docker image to Docker Hub.
- `docker logout`: logs out of Docker Hub.
### Docker Networking
- `docker network ls`: List all Docker networks on your machine.
- `docker network create <network name>`: Create a new Docker network.
- `docker network connect <network name> <container name>`: Connect a Docker container to a network.

### Docker Volumes
- `docker volume ls`: List all Docker volumes on your machine.
- `docker volume create <volume name>`: Create a new Docker volume.
- `docker volume rm <volume name>`: Remove a Docker volume.

### Dockerfile Reference - Basics
- `FROM <image>[:<tag>]`: Specifies the base image to use in the Dockerfile.
- `LABEL <key>=<value> <key>=<value> ...`: Adds metadata to an image in the form of key-value pairs.
- `RUN <command>`: Executes a command inside the image during build.
- `CMD ["<command>", "<arg1>", "<arg2>", ...]` or `CMD <command> <arg1> <arg2> ...`: Specifies the default command to run when starting a container from the image.
- `EXPOSE <port> [<port>/<protocol>] ...`: Documents the ports that the container listens on at runtime.
- `ENV <key>=<value> <key>=<value> ...`: Sets environment variables inside the image.
- `ADD <src> <dest>` or `ADD ["<src>", "<dest>"]`: Copies files or directories from the host machine to the image during build.
- `COPY <src> <dest>` or `COPY ["<src>", "<dest>"]`: Copies files or directories from the host machine


### Docker Compose
- `docker-compose up`: Create and start all containers in a Docker Compose file.
- `docker-compose down`: Stop and remove all containers in a Docker Compose file.
- `docker-compose build`: Build all Docker images in a Docker Compose file.

### docker-compose.yml File Syntax
```yaml
version: '3'
services:
  <service name>:
    image: <image name>
    command: <command>
    ports:
      - "<host port>:<container port>"
    volumes:
      - "<host path>:<container path>"
    environment:
      - <environment variable>=<value>
    depends_on:
      - <service name>
    networks:
      - <network name>
networks:
  <network name>:

```



### Docker Swarm
- `docker swarm init`: Initialize a new Docker Swarm.
- `docker swarm join`: Join a Docker Swarm as a worker node.
- `docker service ls`: List all services running in a Docker Swarm.
- `docker service create`: Create a new service in a Docker Swarm.

