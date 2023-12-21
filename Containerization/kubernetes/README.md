# Script
In this lesson, you will learn about Introduction to Kubernetes and its role in managing containers at scale. So, let's get started.

Containerization has revolutionized the way we package and deploy applications. Containers provide a consistent and isolated environment for applications, making them easier to build, ship, and run across different environments. However, managing containers at scale can be a complex and daunting task. This is where Kubernetes comes in.

### What is Kubernetes?
Kubernetes, often abbreviated as K8s, is an open-source container orchestration platform originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF). Its primary purpose is to simplify the deployment, scaling, and management of containerized applications. 

#### Key Features of Kubernetes
Kubernetes offers several key features that make it a powerful tool for managing containers at scale:
- **Container Orchestration:** Kubernetes automates the deployment, scaling, and orchestration of containers, ensuring that your applications run consistently and reliably.

- **Self-Healing:** Kubernetes continuously monitors the state of your applications and can automatically replace or reschedule containers in case of failures.

- **Load Balancing:** It provides built-in load balancing to distribute traffic across containers, improving the availability and performance of your applications.

- **Scaling:** Kubernetes can scale your applications based on resource usage or other custom metrics, allowing you to adapt to changing workloads.

#### Main components of Kubernetes
- **Master Node:** The master node is the control plane of the cluster, responsible for managing and orchestrating the workloads. It includes components like the API server, controller manager, and scheduler.

- **Node (Minion):** Nodes are the worker machines where containers run. Each node has an agent called the Kubernetes Node (Kubelet) that communicates with the master and manages containers on the node.

- **Pod:** The smallest deployable unit in Kubernetes, a Pod can contain one or more containers sharing the same network namespace and storage. Pods are scheduled onto nodes.

- **Service:** Services provide a stable endpoint for accessing a set of Pods. They ensure that applications can discover and communicate with each other, regardless of the node they are running on.

Now if you want to learn more about Kubernetes and how it does the container orchestration, following these links:

#### Resource 1: https://www.redhat.com/en/topics/containers/what-is-container-orchestration
This article explains the concept of Kubernetes, its benefits, and how it enables you to separate your applications from your infrastructure. It also introduces the Kubernetes platform, which provides tools and services to build, run, and manage containers.

#### Resource 2: https://kubernetes.io/docs/concepts/overview/
This article gives an overview of Kubernetes and its features, such as automated deployment, scaling, and management of containerized applications. It also discusses the core concepts and components of Kubernetes, such as pods, services, deployments, and nodes.

#### Resource 3: https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-deploy-application?tabs=azure-cli
This article shows how to deploy an application on Azure Kubernetes Service (AKS), a managed service that offers a fully integrated Kubernetes environment.

So, that's it for this lesson, see you in the next one.