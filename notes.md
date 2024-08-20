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

What is a Volume?
- A docker volume is a persistent data storage mechanism
- Allows data to be shared between docker containers or between containers and the host machine
- Volumes are stored outside of the container’s filesystem, making them persistent even if the container is deleted.

