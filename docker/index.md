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

## 2.  Architecture
Docker uses a client-server architecture where the Docker client communicates with the Docker daemon, which builds, runs, and manages containers using images and Linux kernel features like namespaces and cgroups.


{{< mermaid >}}

graph LR;

    A[Docker Client ] -->|Rest Api| B(Docker Daemon/Dockerd)


    B --> C[Images]

    B --> D[Containers]

    C --> E[Docker Registry]

{{< /mermaid >}}

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


## Running SpringBoot App on Docker


{{< copybox title="1. Check Running Containers" >}}
docker ps
{{< /copybox >}}

{{<copybox title="2. List All Files in the Container (JDK Environment)">}}
docker exec container_name ls -a<br>
# Lists all folders and files in the container's root directory.
{{</copybox>}}


{{< copybox title="3. Check Contents of /tmp Directory" >}}
docker exec container_name ls /tmp <br>
# It will contain only one file in /tmp at the initial stage.
{{< /copybox >}}

{{< copybox title="4. Copy the Spring Boot JAR File into the Container" >}}
docker cp target/rest-demo.jar container_name:/tmp <br>
# This copies the rest-demo.jar into the container’s /tmp directory.
{{< /copybox >}}

{{< copybox title="5. Verify the JAR File is Present" >}}
docker exec container_name ls /tmp <br>
# The rest-demo.jar file will be available in addition to the existing content.
{{< /copybox >}}

{{< copybox title="6. Commit the Container to Create a New Docker Image" >}}
docker commit container_name telusko/rest-demo:v1 <br>
# Creates a new Docker image named telusko/rest-demo with tag v1 from the current container state.
{{< /copybox >}}

{{< copybox title="7. List Docker Images" >}}
docker images <br>
# Verifies that telusko/rest-demo:v1 image has been created successfully.
{{< /copybox >}}

{{< copybox title="8. Default Behavior: JShell" >}}
docker run telusko/rest-demo:v1 <br>
# When running telusko/rest-demo:v1, the container defaults to JShell.
{{< /copybox >}}

{{< copybox title="9. Set Default Command to Run JAR Using --change" >}}
docker commit --change='CMD ["java", "-jar", "/tmp/rest-demo.jar"]' container_name telusko/rest-demo:v2 <br>
# This sets the default command to run the JAR directly when the image is run.
{{< /copybox >}}

{{< copybox title="10. Run the Updated Image (v2)" >}}
docker run telusko/rest-demo:v2 <br>
# This will now run the Spring Boot application from the JAR instead of entering JShell.
{{< /copybox >}}

{{< copybox title="11. Map Ports While Running the Container" >}}
docker run -p 8081:8081 telusko/rest-demo:v2 <br>
# Maps port 8081 of the container to 8081 on the host machine.
{{< /copybox >}}



{{< admonition type=abstract title="Resources" open=true >}}
- Official docs: https://docs.docker.com
- Dockerfile reference: https://docs.docker.com/engine/reference/builder/
- Docker Compose: https://docs.docker.com/compose/
- Image scanning: https://github.com/aquasecurity/trivy
{{< /admonition >}}


 Thanks for reading! 


<div style="position: relative; background: #f2f2f2; color: #333; padding: 16px; border-radius: 6px; font-family: monospace; border: 1px solid #ccc;">

  docker run -p 8081:8081 telusko/rest-demo:v2
</div>



{{< copybox title="Run Spring Boot Container" >}}
docker run -p 8081:8081 telusko/rest-demo:v2
{{< /copybox >}}

