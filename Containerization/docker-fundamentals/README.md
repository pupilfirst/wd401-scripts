# Script
In this lesson, you will learn more about Docker, what is dockerfile, and how we can build a custom container. So let's get started.

Today, Docker has became the go-to tool for developers and operations teams. With Docker, you can seamlessly package applications and their dependencies into lightweight, portable containers. 

#### Now, let's understand the Docker Containerization

Containerization is a technology that enables you to encapsulate an application and all its dependencies within a self-contained unit called a **container**. These containers are **isolated from one another** and from the host system, ensuring that an application runs consistently across different environments. Think of it as shipping your application with everything it needs to work, neatly packed into a single box.

#### In Docker, you ca create custom container images with Dockerfile
One of the core concepts in Docker is the Dockerfile. A Dockerfile is a simple text file that contains a set of instructions for building a custom container image. So, to create a Docker image, you've to go through the following steps:

##### 1. Choose a Base Image:
Start by selecting a base image that closely matches the runtime environment your application requires. Common choices include official Linux distributions like Ubuntu or Alpine.

##### 2. Define Application Setup:
Use Dockerfile instructions to define how your application should be set up within the container. This may include installing software, copying files, and configuring settings.

##### 3. Expose Ports and Set Environment Variables:
Specify which ports your application needs to listen on and set any environment variables it requires.

##### 4. Build the Docker Image:
Run the docker build command, pointing to your Dockerfile, to create the custom image.

##### 5. Run Containers from Your Custom Image:
Once the image is built, you can use it to run containers with your application. These containers will be consistent and easily reproducible.

You can learn more about Docker, using the following links:

#### Reference 1: https://docs.docker.com/get-started/overview/
This article explains the concept of Docker, its benefits, and how it enables you to separate your applications from your infrastructure. It also introduces the Docker platform, which provides tools and services to build, run, and manage containers.

#### Reference 2: https://linuxhandbook.com/create-custom-docker-image/
This article shows how to create a custom Docker image with Dockerfile using an example of Alpine Linux with Vim editor. It covers the steps of creating a Dockerfile, building an image, and running a container. It also explains the syntax and instructions of a Dockerfile.

#### Reference 3: https://www.freecodecamp.org/news/run-multiple-containers-with-docker-compose/
This article demonstrates how to run multiple containers with Docker Compose using an example of a project that uses MySQL, Python, Node.js, .NET, and PHP. It covers the steps of creating a sample application, a Dockerfile, and a docker-compose.yml file for each technology.

So, that's it for this lesson, see you in the next one.