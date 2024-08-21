What is Docker? <br>
Docker is open-source platform for building, deploying, and managing containerzied applications.
- Ensures consistency
- Portability
- Helps track application 

What is a Docker Image?
- A docker image is a lightweight, standalone, executable package that includes everything needed to run an application: code, libraries,runtime, and system tools.
- The image is the blueprint for creating containers

What is Docker Container?
- A container is a running instance of an image
- We can run multiple containers from the same image
- Containers are isolated from each other and the host system but share the same operating system kernel.

What is a Dockerfile?
- A dockerfile is a text file which contains the instructions for bilding a docker image

Common dockerfile commands:
- FROM: Specifies the base image to use for the Docker image
- WORKDIR: Sets the working directory inside the container. All subsequent commands in the Dockerfile will be run from this directory.
- COPY: Copies files or directories from the host machine to the image
- RUN: Executes commands in the shell within the container during the image build process. Typically used to install software packages.
- EXPOSE: Informs Docker that the container will listen on the specified network ports at runtime.
- ENV: Sets environment variables in the container.
- ARG: Defines a variable that users can pass at build-time to the image 
- VOLUME: Creates a mount point with a specified path and marks it as a volume. Essentially specifying a location inside the container where you can connect external storage
- CMD: Specifies the default command to run when a container is started. Only one CMD can be used per Dockerfile.
- ENTRYPOINT: Similar to CMD, but less flexible

What is a Docker Volume?
- A docker volume is a persistent data storage mechanism
- Allows data to be shared between docker containers or between containers and the host machine
- Volumes are stored outside of the container’s filesystem, making them persistent even if the container is deleted.

What is a Docker Network?
- A Docker network is a virtual network that allows containers to communicate with each other and with other networks.
- This allows containers to share information and services 

Docker workflow:
- Docker client - is the user interface for interacting with Docker
- Docker daemon - is the background service that does the running, building and managing of containers. It listens to commands from the docker client and executes it.
- Docker registry/hub - is a centralized repo of docker images, containing both public and private images

Common docker commands:
- docker pull: pulls a pre-built Docker image from Docker Hub
- docker run: creates a container from an image
  - -d: Runs the container in detached mode (in the background).
  - -p: Maps a port on the host to a port on the container.
  - -v: Is used to mount volumes, which allows you to map a directory or file from your host machine to the container
  - -it: Runs the container in interactive mode
- docker ps: List all the running containers
- docker stop <container_id>: Stops a running container
- docker rm <container_id>: Removes a stopped container
- docker build: Used to build your own custom image from a dockerfile
- docker container prune: This removes all stopped containers
- docker init: Initializes our app with all needed files

What is Docker Compose? <br>
Docker Compose is a tool that simplifies running multi-container Docker applications. With Docker Compose, you can define and manage multi-container applications using a YAML file, which makes it easy to start, stop, and manage containers as a group.
- compose.yml: Is the configuration file where you define your application's services, networks, and volumes. It describes how your containers should be built, configured, and connected
- service: A service represents a container in your application. Each service runs a specific image and has its own configuration.
- networks: Docker Compose automatically creates a network for your services to communicate with each other. Can also define custom networks.
- volumes: Volumes allow you to persist data and share files between your host machine and the containers, or between containers

Common docker compose commands:
- docker-compose up: This command starts and runs all the services defined in the docker-compose.yml file. If the images aren’t already built, it will build them.
- docker-compose down: Stops and removes all containers, networks, and volumes created by 'docker-compose up'
- docker-compose build: Builds the Docker images for the services defined in the compose.yml file.
- docker-compose ps: Lists all the running containers defined in the compose.yaml file
