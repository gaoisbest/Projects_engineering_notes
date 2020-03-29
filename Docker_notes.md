# Introduction
- **Image**: includes everything needed to run an application - the code or binary, runtimes, dependencies, and any other filesystem objects required
- **Container**: a running process, with some added encapsulation features applied to it in order to keep it isolated from the host and from other containers
- [Official documentation](https://docs.docker.com/get-started/)

# Build image
## Step 1: `cd` to project folder, new a Dockerfile
- Dockerfile describes step-by-step recipe on how to build up your image
- Example

```
# Use the official image as a parent image
FROM node:current-slim

# Set the working directory
WORKDIR /usr/src/app

# Copy the file from your host to your current location
COPY package.json .

# Run the command inside your image filesystem
RUN npm install

# Inform Docker that the container is listening on the specified port at runtime
EXPOSE 8080

# Run the specified command within the container.
CMD [ "npm", "start" ]

# Copy the rest of your app's source code from your host to your image filesystem
COPY . .
```
## Step 2: build the image
`docker build --tag hellodocker:1.0 .`

## Step 3: run the image
`docker run --publish 88:80 --deatch --name hello_docker hellodocker:1.0`

- `--publish` maps host’s port 8000 to the container’s port 8080
- `--detach` runs this container in the background
- `--name` specifies a name with which you can refer to your container in subsequent commands

## Other commands
- **Stop** the running container: `docker stop hello_docker`
- **Remove** the container: `docker rm hello_docker`
- **Remove** the image: `docker image rm hello_docker`
- **List** all images: `docker image ls`
- **Version**: `docker --version`
