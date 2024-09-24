# Docker Containers:

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
