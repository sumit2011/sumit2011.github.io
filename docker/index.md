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

## 3. Key concepts
### 3.1 Virtualization
it is technique that allows the computer to act like multiple independent computers by creating virtual versions of hardware and software. somehow docker uses OS-level virtualization which is called containerization.

{{< mermaid >}}
graph LR;

    A[Hardware ] --> B(Host OS) 

    B --> C[Hypervisor]

    C --> D[Guest OS 1] --> E[App1]

    C --> F[Guest OS 2] --> G[App2]

{{< /mermaid >}}

### 3.2 Containerization
It is a lightweight form of virtualization where apps run in isolated environments called continers.Containers share the host kernel and isolation is provided by namespaces (PID, mount, network, user, etc.) and cgroups for resource limits.\
**Benefits:** Fast, secure, portable, scalable, lightweight.

{{< mermaid >}}

graph LR;

    A[Hardware ] --> B(Host OS) 

    B --> C[Docker Engine]

    C --> D[Container 1] --> E[App1]

    C --> F[Container 2] --> G[App2]

{{< /mermaid >}}

## 4. Main Components

**Docker Engine:** The runtime that builds, runs, and manages containers (via the Docker CLI and API).


**Container:** Containers are isolated processes for each of the app's components. all the components like frontend react, backend python, postgres database run in the completely isolated environment.Containers are self-contained, isolated, independent and portable.

**Image:** To share the container we need image. A Container image is a standerized package that includes all of the files, binaries and configuration to run the container.
THere are two imp principle of images
1. Images are immutable: once an image is created it cant be modifie. you can only make new image or add changes on top of it.

2. Container images are composed of layers. Each layer represents a set of file system changes that add, remove, or modify files.

**Docker Hub** Docker hub is the default global marketplace for storing and distributing images. it has more than 1 lac images created by the devs. we can dwnld and run the images.

**Registry:** An image registry is a centralized location for storing and sharing the container images. It can be either public or private.(Docker Hub, GitHub Container Registry, private registries).

**Volume:** Persistent storage mounted into containers.It is separate from a container's lifecycle. It is used to store data so it doesn't get lost when a container stops, restart or deleted.

**Network:** Network means a virtual communication layer that allows containers to talk to each other and to the outside world. It connects containers securely.

**Dockerfile:** A text file with instructions (`FROM`, `COPY`, `RUN`, `CMD`) used to build an image.

**Docker Compose:** A tool for defining and running multi-container applications with a YAML file.


## 5. Common Docker commands
Most Commonly used docker commands

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


## 6. Container & Image Lifecycle Commands

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


### 6.1 Step-by-Step: Docker Workflow
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


### 7. Running First Container (Hello World)

***Step 1.*** Check Docker Version
```bash
docker --version
```

***Step 2.*** Run a test container using the hello-world image to verify Docker installation.
```bash
docker run hello-world
```

***Step 3.*** Pull the hello-world image from Docker Hub.
```bash
docker pull hello-world
```

***Step 4.*** Check all currently runnings containers.

```bash
docker ps
```

{{< admonition type=tip title="Output" open=true >}}
```bash
 CONTAINER ID   IMAGE                      COMMAND                  CREATED          STATUS          PORTS                      NAMES
 a1f7a4bb3a27   docker/welcome-to-docker   "/docker-entrypoint.â¦"   11 seconds ago   Up 11 seconds   0.0.0.0:8080->80/tcp       gracious_keldysh
 ```
{{< /admonition >}}


***Step 5.*** Show all containers, both running and stopped.

```bash
docker ps -a
```

***Step 6.*** ist all Docker images downloaded and available locally.

```bash
docker images
```

## 8. Running SpringBoot App on Docker
To run the spring boot web app on the docker we need the jar file. so 1st create the jar file then upload the jar file to the container.
### 8.1 Package the Web App
This document provides a list of basic Docker CLI commands used in the lecture.

***Step 1:*** Package the Project Using Maven

```bash
mvn package
```

***Step 2:*** Run the JAR File
```bash
java -jar target/rest-demo.jar
```

### 8.2 Run the App on Docker


***Step 1:*** Check Running Containers
```bash
docker ps
```

***Step 2.*** List All Files in the Container (JDK Environment)
```bash
docker exec container_name ls -a
```
Lists all folders and files in the container's root directory.


***Step 3.*** Check Contents of /tmp Directory" 
```bash
docker exec container_name ls /tmp 
```
It will contain only one file in /tmp at the initial stage.


***Step 4.*** Copy the Spring Boot JAR File into the Container
```bash
docker cp target/rest-demo.jar container_name:/tmp 
```
This copies the rest-demo.jar into the container’s /tmp directory.

***Step 5.*** Verify the JAR File is Present
```bash
docker exec container_name ls /tmp 
```
The rest-demo.jar file will be available in addition to the existing content.


***Step 6.*** Commit the Container to Create a New Docker Image
```bash
docker commit container_name n4ksum/rest-demo:v1
```
Creates a new Docker image named n4ksum/rest-demo with tag v1 from the current container state.


***Step 7.*** List Docker Images
```bash
docker images 
```
Verifies that n4ksum/rest-demo:v1 image has been created successfully.

***Step 8.*** Default Behavior: JShell
```bash
docker run n4ksum/rest-demo:v1 
```
When running n4ksum/rest-demo:v1, the container defaults to JShell.

***Step 9.*** Set Default Command to Run JAR Using --change
```bash
docker commit --change='CMD ["java", "-jar", "/tmp/rest-demo.jar"]' container_name n4ksum/rest-demo:v2 
```
This sets the default command to run the JAR directly when the image is run.

***Step 10.*** Run the Updated Image (v2)
```bash
docker run n4ksum/rest-demo:v2 
```
This will now run the Spring Boot application from the JAR instead of entering JShell.


***Step 11.*** Map Ports While Running the Container" 
```bash
docker run -p 8081:8081 n4ksum/rest-demo:v2
```
Maps port 8081 of the container to 8081 on the host machine.



## 9. Running JDK Docker Container

This document provides a list of basic Docker CLI commands used in the lecture.

### 9.1 JShell
- JShell is a **REPL (Read-Eval-Print Loop)** for Java introduced in Java 9.
- It allows running Java code interactively, without needing to compile and run entire class files.


### 9.2 Pull OpenJDK Docker Image
**1. Search for the OpenJDK image on Docker Hub**

```bash
docker search openjdk
```

**2. Pull a specific OpenJDK Image**

```bash
docker pull openjdk:22-jdk
```

**3.Check Available Images**

```bash
docker images
```

**4. Run the OpenJDK image**

```bash
docker run openjdk:22-jdk
```

**5. Run OpenJDK image in interactive mode**

```bash
docker search openjdk
```
> The `-it` flag starts the container in **interactive terminal mode**.

**6. Check Running Containers**

```bash
docker ps
```


### 9.3 Enter JShell inside the Container
```bash
jshell
int num = 8;
System.out.println("Hello World");
/exit  #to exit from JShell
```
> Make sure the openjdk image version you pull supports jshell


## 10 Docker File for Docker Images
Build the Docker Image, Navigate to the directory that contains your `Dockerfile` and run:

```bash
docker build -t n4ksum/rest-demo:v3 .
# This builds a Docker image named n4ksum/rest-demo with tag v3 using the current directory (.) as the build context.
```


List Available Docker Images
```bash
docker images
```


Run the Docker Image with Port Mapping
```bash
docker run -p 8081:8081 n4ksum/rest-demo:v3
# This runs the container from the newly built image and maps port 8081 of the host to port 8081 of the container.
```

## 11. Docker Compose

Clean and Package the Application:
Use Maven to clean and create a JAR package of the Spring Boot project:
```bash
mvn clean package
```


Build and Start Docker Containers:
Use Docker Compose to build the images and start the containers:
```bash
docker-compose up --build
```
> This will use the docker-compose.yml file to build the application.


List Docker Images
```bash
docker images
```

## 12. Running Multiple Containers

This document provides a list of basic Docker CLI commands used in the lecture.

Stop and Remove All Running Containers
```bash
docker-compose down
```


Clean and Package the Spring Boot App
```bash
mvn clean package -DskipTests
```


Build and Start Containers:
```bash
docker-compose up --build
```


Check Running Containers:
```bash
docker ps
```


View Docker Networks:
To list all Docker networks on your system:
```bash
docker network ls
```



{{< admonition type=abstract title="Resources" open=true >}}
- Official docs: https://docs.docker.com
- Dockerfile reference: https://docs.docker.com/engine/reference/builder/
- Docker Compose: https://docs.docker.com/compose/
- Image scanning: https://github.com/aquasecurity/trivy
{{< /admonition >}}


 Thanks for reading! 
