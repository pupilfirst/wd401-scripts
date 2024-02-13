# Script
In this lesson, you will learn more about application containerization. 

Now, you might ask: *What is containerization?*

Well, containerization is a technology that allows you to package an application and all its dependencies into a single container. This container is like a standalone unit that can run consistently across different computing environments, such as your laptop, a server in a data center, or in the cloud.

Think of it as a virtual box that contains everything your application needs to run: the code, libraries, settings, and even the operating system components if necessary. This container is isolated from the host system and other containers, ensuring that the application runs consistently regardless of where it's deployed.

Containerization provides several benefits:

**1. Portability:** You can easily move containers between different environments without worrying about compatibility issues.

**2. Consistency:** Containers ensure that an application behaves the same way in development, testing, and production environments.

**3. Efficiency:** They are lightweight and efficient, as multiple containers can run on a single host without the overhead of running full virtual machines.

**4. Isolation:** Each container is isolated from others, enhancing security and preventing conflicts between applications.

**5. Scalability:** Containers can be quickly scaled up or down to accommodate changing workloads.

Some of the popular containerization technologies include Docker, Podman etc. and the most popular container orchestration platforms is: Kubernetes.

### What is Docker?
Docker is a leading containerization platform that allows you to package applications and their dependencies into containers. These containers are lightweight, portable, and isolated from the host system and other containers. Docker simplifies the process of building, deploying, and managing applications by encapsulating them in containers.

### What is Kubernetes?
It is an open-source container orchestration platform originally developed by Google. It helps you automate the deployment, scaling, and management of containerized applications. Kubernetes is designed to handle complex containerized workloads and offers features like load balancing, auto-scaling, and self-healing.

You can learn more about containerization, using the following links:

#### Resource 1: https://www.ibm.com/topics/containerization
This article explains the concept of containerization, its history, benefits, and use cases. It also introduces the roles of Docker and Kubernetes in creating and managing containers.

#### Resource 2: https://opensource.com/article/20/12/containers-101
This article covers the basics of containers, such as how they work, how they differ from virtual machines, and how they enable agile and DevOps practices. It also discusses the features and functions of Docker and Kubernetes.

#### Demo
Now, let me show you, how we've containerised a Node.Js application using Docker.
> Action: Open the application in VsCode
> 1. Show the docker file
> 2. Show how we start the application
> 3. Show how we can access application files inside Docker

So, that's it for this lesson, see you in the next one.