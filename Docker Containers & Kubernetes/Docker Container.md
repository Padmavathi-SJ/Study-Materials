# Docker Containers:

## Difference between docker containers and Kubernetes:
### In our application, for each and every component we can make a container.
### so to manage our containers, we want a "Container Orchestrator Tool" such as "Kubernetes"
### so kubernetes is "Container Orchestrator Tool"

## What is container:
* A unit of software and deployment[code, Runtime, System tools, System libraries].

### why containers?
1. Move faster by deploying smaller units.
2. Use fewer resources.
3. Fit more into the same host.
4. Faster automation
5. Portability
6. Isolation
   
* Because it is faster to deploy something small than something big like a complete monolithic system.
* when using CI/CD techniques they are a lot faster to deploy.
* we can run hte anywhere.
* They are isolated each other, meaning that if one fails, it will not take the whole system down with it.

### What is virtualized?
1. Virtual Machines:
     * Large footprint
     * Slow to boot
     * Ideal for long running tasks
2. Container
     * Lightweight
     * Quick to start(it does not have to boot)
     * Portable
     * Ideal for short lived taskes
* Our containers replacing Virtual Machines.

* Containers are made of layers
    1. Application   
    2. Customization                                   
    3. Base OS(windows or linux) 

       
## Container Registry:
* Centralized container repository
* Think Github for container
* Docker Hub
    -- https://hub.docker.com/
* Cloud providers
    -- AWS, Azure, Google cloud

## Orchestrator:
1. Manage
     * Infrastructure
     * Containers
     * Deployment
     * Scaling
     * Failover
     * Health monitoring
     * App upgrades, Zero-Downtime deployments
2. Install you own
     * Kubernetes, Swarm, Service Fabric
3. Orchestrators as a service
     * Azure Kubernees Service, Service Fabric, Google cloud, AWS

## Docker:
### what is docker?
* The company
* the platform
* the container runtime
* Runtime & image specs
* Acquired Docker Enterprise in 2019 in MIRANTIS

* Docker provides.
* An open source container runtime
* Mac, Windows & Linux support
* Command line tool
* "Dockerfile" --> file format for building container
* Windows let your run Windows and Linux containers

* download/install docker desktop.
* and create an account in dockerhub.com

### Docker CLI(Command Line Interface) Cheat Sheet-Management:
1. docker info
     -- Display system information
2. docker version
     -- Display the system's version
3. docker login
     -- Log in to a Docker registry

### Docker CLI Cheat Sheet - Running and Stopping for containers:
1. docker pull [imageName] ---> Pull an image from a registry
2. docker run [imageName] ---> Run containers
3. docker run -d [imageName] ---> Detached mode
4. docker start [containerName] ---> start stopped containers
5. docker ps ---> List running containers
6. docker ps -a ---> List running and stopped containers
7. docker stop [containerName] ---> Stop containers
8. docker kill [containerName] ---> kill containers
9. docker image inspect [imageName] ---> Get image info


### Docker CLI Cheat Sheet - Limits
1. docker run --memory="256m" nginx ---> Max memory
2. docker run --cpus=".5" nginx ---> Max CPU

### Docker CLI Cheat Sheet - Cleaning up
1. docker rm [containerName] --> removes stopped containers
2. docker rm $(docker ps -a -q) ---> Removes all stoped containers
3. docker images ---> Lists images
4. docker rmi [imageName] --> Delete the image
5. docker system prune -a ---> Removes all images not in use by any containers.

### Docker CLI Cheat Sheet - Building
1. docker build -t [name:tag] .  ---> Builds an image using a Dockerfile located in 
                                      the same folder
2. docker build -t [name:tag] -f [fileName] ---> Builds an image using a Dockerfile  located in a different folder
3. docker tag [imageName] [name:tag]  ---> Tag an existing image

### Docker Compose:
* The below services can run Docker Compose files:
    1. Azure App Services
    2. AWS ECS
    3. Virtual Machines
 
### Docker Compose Cheat Sheet:
1. docker compose build ---> Build the image
2. docker compose start ---> Start the containers
3. docker compose stop  ---> Stop the containers(but still in memory)
4. docker compose u -d ---> Build and start
5. docker compose ps ---> List what's running
6. docker compose rm ---> Remove from memory
7. docker compose down ---> Stop and remove
8. docker compose logs ---> Get the logs
9. docker compose exec [container] bash ---> Run a command in a container

### Compose V2 - NewCommands
1. docker compose --project-name test1 up -d ---> Run an instance as a project
2. docker compose -p test2 up -d ---> Shortcut
3. docker compose ls ---> Lists running projects
4. docker compose cp ---> Copy files from the container
   [containerID] : [SRC_PATH] [DEST_PATH]
5. docker compose cp ---> Copy files to the container
   [SRC_PATH] [containerID] : [DEST_PATH]

   
### Importance of Dockers:
* We can run on any machine or OS.
* docker containers are immutable
* We can scla easily
* they are highly portable

