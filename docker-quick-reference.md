# Docker Commands: Quick Reference

General structure of a docker command:

`docker [--options]`

Examples:

```docker-cli
# Output Docker version
docker --version

# View Docker help file
docker --help
```

General structure of Docker standalone command:

```docker <command> [--options]```

Standalone command examples:

```docker-cli
# View Docker information
docker info

# View Docker images on host
docker images
```

General structure of Docker management command:

`docker <management command> <sub-command> [--options] <object>`

Example management command to launch new container with ngix image:

`docker container run -it nginx`

General breakdown of a Docker Command:

| **Docker CLI** | **Docker command** | **Options** | **Object** |
|:---:|:---:|:---:|:---:|
| Structure | docker | &lt;command&gt; &lt;subcommand&gt; | [--options] | &lt;object&gt; |
| Example | docker | container run | -it | httpd |
| Details | Invokes Docker and passes additional commands and options. | Command names must be written exactly as noted in the documentation. | Options are passed to the command and control how it behaves. There are two notations for options, see below. | Placeholder for an object as the target of the operation. For Docker objects, such as containers and images, the ID is the name or hash of the object. |

## Docker Standalone Commands

```docker-cli
# view help file
docker --help

# view the current version
docker --version

# view system wide information regarding Docker installation
docker info

# log in to a container registry or cloud backend
docker login

# log out
docker logout
```

## Docker Image Commands

Docker images are the basis of containers. An Image is an ordered collection of root filesystem changes and the corresponding execution parameters for use within a container runtime. An image typically contains a union of layered filesystems stacked on top of each other. An image does not have state and it never changes.

```docker-cli
# Create a docker image from a Dockerfile
docker image build

# View steps to create a Docker image from a Dockerfile
docker image history <image>

# Create a Docker image from a tar archive file
docker image import <archive file>

# View detailed information of an image
docker image inspect <image>

# Load image archive created with "docker image save"
docker image load

# List images available on the system
docker image ls

# Remove unused Docker images
docker image prune

# Pull Docker image from registry
docker image pull <image>

# Push Docker image to a registry
docker image push <image>

# Remove a Docker image from the system
docker image rm <image>

# Create an image archive with all layers from 1 image
docker image save <image>

# Tag a Docker image
docker image tag <source image> <target image>
```

## Docker Container Commands

A container is a runtime instance of a docker image.

A Docker container consists of

+ A Docker image
+ An execution environment
+ A standard set of instructions

The concept is borrowed from shipping containers, which define a standard to ship goods globally. Docker defines a standard to ship software.

```docker-cli
# Display the containers running on the host
docker container ls

# Display the status information of running containers
docker container stats

# Start a new Docker container from a specified image
docker container run <image>

# Create a new image from the changes of a running container
docker container commit <container>

# Provide a running container with local standard input, output, and error streams
docker container attach <container>

# Display log information of a container
docker container logs <container>

# Display detailed information of a container
docker container inspect <container>

# Renew the configuration of a container
docker container update <container>

# Rename the a container
docker container rename <container> <new name>

# Show port assignment of a container
docker container port <container>

# Pause active processes in a container
docker container pause <container>

# Resume activity in a paused container
docker container unpause <container>

# Execute a command within a running container
docker container exec <container> <command>

# Stop the execution of a running container
docker container stop <container>

# Resume the execution of a stopped container
docker container start <container>

# Restart a docker container, stops then starts container
docker container restart <container>

# List the running processes in a container
docker container top <container>

# Kill a running container
docker container kill <container>

# Remove a container
docker container rm <container>

# Remove all stopped containers from the system
docker container prune

# Copy files and folders from container and local file system
docker container cp <container>:<source path> <destination path>

# Display changes to the file system of a container
docker container diff <container>

# Output the file system as a tar archive (reduces all layers to 1)
docker container export <container>
```
