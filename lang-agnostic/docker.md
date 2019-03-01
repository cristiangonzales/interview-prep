Docker Review
---
### Hypervisor Versus Docker

| Features | Hypervisors | Docker |
|----------|-------------|--------|
| **Default Security Support** | To a great degree | To a slightly less degree |
| **Memory on disk required** | Complete OS plus app | App requirement only |
| **Time taken to start up** | Longer -> boot OS plus app loading | Shorter -> kernel already running, only app needs to start |
| **Portability** | Portable with proper preparation | Portable within image format |
| **Operating System** | Supports multiple OS'es | Uses host OS |

---
### What is Docker?
* Containerization platform which packages an app and its dependencies in a container so the app works in any environment
* Docker containers wrap software (the app) in a complete filesystem that contains everything needed to run (e.g. runtime, system tools, system libraries, anything that can be installed on a server)
* Thus, software will run the same regardless of the environment
* VMs have their own OS, while Docker uses the host OS

### What is a Docker image?
* Used to create containers are created with the `docker build` command, and will produce a container with the `docker run` command
* Images are stored in the Docker registry because they can become large
* Images are composed of *layers* of other images so not a lot of data is sent over the network

### What is a Docker container?
* Docker containers include the application and dependencies but share the host kernel with other containers, running as isolated processes in the user space on the host OS
* Docker containers are not tied to any specific infrastructure, and hence, they can be ran anywhere
* Created by running a build Docker image or using a Docker Hub image (containers are basically runtime instances of Docker images)

### What is Docker Hub?
* Cloud based registry service to link repos, build/test/store images, and links to the Docker cloud (for associated accounts)

### How is Docker different from other container technologies?
* Docker containers are easy to deploy in the cloud
* You can have more applications running on the same hardware versus other technologies
* Docker makes for easy-to-develop, ready-to-run containerized applications
* Docker makes managing/deploying applications easier

### What is Dockerfile used for?
* Dockerfile is a text document that contains all the commands a user could call, and is generally used to assemble an image
* It is an automated build that executes several instructions in succession

### What is Docker Swarm?
* Native clustering for Docker
* Turns pool of Docker hosts into a single, virtual Docker host
* Any tool that communicates with a Docker daemon can use Swarm to scale multiple hosts

### How far do Docker containers scale?
* Large web deployments all run on container technology, at a scale of hundreds of thousands to millions of containers in parallel

### Do I lose my data when the Docker container exits?
* All data written to disk is preserved in its container, so the only case where you lose data is if you delete that container
