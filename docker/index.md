# Docker — Containers Simplified

***Docker packages applications and their dependencies into portable containers so they run consistently across environments.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to jump to the section you need._
{{< /admonition >}}

## 1. Introduction

Docker is a containerization platform that automates the deployment of applications inside lightweight, portable containers. A container bundles your application code with its runtime, system tools, libraries, and settings — ensuring the app runs the same on a developer laptop, CI server, or production host.
It has several features like:
- **Consistency:** "Works on my machine" problems vanish.
- **Isolation:** Containers isolate processes and dependencies.
- **Portability:** Images run anywhere with the Docker runtime.
- **Efficiency:** Containers are lightweight compared to full VMs.
- **Speed:** Faster startup and simplified CI/CD.



## 2. Key concepts
### 2.1 Virtualization
it is technique that allows the computer to act like multiple independent computers by creating virtual versions of hardware and software. somehow docker uses OS-level virtualization which is called containerization.

Architecture:

{{< mermaid >}}

graph LR;

    A[Hardware ] --> B(Host OS) 

    B --> C[Hypervisor]

    C --> D[Guest OS 1] --> E[App1]

    C --> F[Guest OS 2] --> G[App2]

{{< /mermaid >}}

### 2.2 Containerization
It is a lightweight form of virtualization where apps run in isolated environments called continers.Containers share the host kernel and isolation is provided by namespaces (PID, mount, network, user, etc.) and cgroups for resource limits.\
**Benefits:** Fast, secure, portable, scalable, lightweight.

Architecture:

{{< mermaid >}}

graph LR;

    A[Hardware ] --> B(Host OS) 

    B --> C[Docker Engine]

    C --> D[Container 1] --> E[App1]

    C --> F[Container 2] --> G[App2]

{{< /mermaid >}}

### 2.3 Components

**Docker Engine:** The runtime that builds, runs, and manages containers (via the Docker CLI and API).

**Image:** An immutable, layered artifact built from a `Dockerfile`. Images are versioned and pushed to registries.

**Container:** A running instance of an image (an isolated process namespace).

**Registry:** Storage for images (Docker Hub, GitHub Container Registry, private registries).

**Volume:** Persistent storage mounted into containers.

**Network:** Bridge, host, or overlay networks for service connectivity.

**Dockerfile:** A text file with instructions (`FROM`, `COPY`, `RUN`, `CMD`) used to build an image.

**Docker Compose:** A tool for defining and running multi-container applications with a YAML file.


## 3. Common Docker commands


| Command             | Description                                       |
|---------------------|---------------------------------------------------|
| `docker run`        | Create and run a new container from an image     |
| `docker exec`       | Execute a command in a running container         |
| `docker ps`         | List running containers                          |
| `docker ps -a`      | List all containers (running and stopped)        |
| `docker build`      | Build an image from a Dockerfile                 |
| `docker bake`       | Build from a file                                |
| `docker pull`       | Download an image from a registry                |
| `docker push`       | Upload an image to a registry                    |
| `docker images`     | List all downloaded Docker images                |
| `docker login`      | Authenticate to a Docker registry                |
| `docker logout`     | Logout from a Docker registry                    |
| `docker search`     | Search Docker Hub for images                     |
| `docker version`    | Show Docker version info                         |
| `docker info`       | Display system-wide Docker info                  |


## 4. Container & Image Lifecycle Commands

**List All Containers**
`
docker ps -a
`

**Delete a container**
`docker rm <container_id>`


**List All Images**
`docker images`

**Delete an image**
`docker rmi <image_id>`

{{< admonition type=note title="Note" open=true >}}
- Every time you run a Docker container, a **new container ID** is generated.
- Remove containers before deleting their images.

{{< /admonition >}}


### 4.1 Step-by-Step: Docker Workflow
***Step 1.*** Search for Images on Docker Hub
`docker search <image_name>`

***Step 2.*** Pull an image from Docker Hub 
`docker pull <image_name>`

***Step 3.*** Check Containers (None Created Yet)
`docker ps -a`

***Step 4.*** Create a Container from the Image
`docker create <image_name>`


***Step 5.*** Verify Container is Created
`docker ps -a`

***Step 6.*** Start the Container
`docker start <container_id or container_name>`


***Step 7.*** Confirm Container is Running
`docker ps -a`

***Step 8.*** Pause the Container (Optional)
`docker pause <container_id>`

***Step 9.*** Stop the container
`docker stop <container_id>`

***Step 10.*** Remove the container
`docker rm <container_id>`


***Step 11.*** Verify Container is Removed
`docker ps -a`

## Docker Architecture
Docker uses a client-server architecture where the Docker client communicates with the Docker daemon, which builds, runs, and manages containers using images and Linux kernel features like namespaces and cgroups.


{{< mermaid >}}

graph LR;

    A[Docker Client ] -->|Rest Api| B(Docker Daemon/Dockerd)


    B --> C[Images]

    B --> D[Containers]

    C --> E[Docker Registry]

{{< /mermaid >}}



## Resources & further reading
- Official docs: https://docs.docker.com
- Dockerfile reference: https://docs.docker.com/engine/reference/builder/
- Docker Compose: https://docs.docker.com/compose/
- Image scanning: https://github.com/aquasecurity/trivy




 Thanks for reading! 
