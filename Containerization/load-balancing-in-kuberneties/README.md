# Text
In this lesson, you will learn about load balancing in Kubernetes. So, let's get started.

Load balancing is the process of distributing network traffic equally over a set of resources that support an application. To do that we distribute the network traffic equally which will result in better availability, scalability, security, and performance for the application.

In this context, Kubernetes offers several options for load balancing, depending on the type of application and the requirements of the workload.

In general, there are two types of load balancing that Kubernetes provide:

1. **Internal:** Internal load balancing refers to load-balancing traffic within a Kubernetes cluster. Internal load balancing is fairly simple and is handled by the ClusterIP service.

2. **External:** External load balancing is used to expose our services outside our cluster. Kubernetes provides three types of external load balancing: NodePort, LoadBalancer, and Ingress.

Now, if you want to learn more about how we can implement that, you can follow these resources:

#### Resource 1: https://tamerlan.dev/load-balancing-in-kubernetes-a-step-by-step-guide/
This article explains the concept of load balancing in Kubernetes and how it ensures high availability and performance for applications. It also covers the different types of services that Kubernetes provides for load balancing, such as ClusterIP, NodePort, LoadBalancer, and Ingress.

#### Resource 2: https://kubernetes.io/docs/tutorials/kubernetes-basics/scale/scale-intro/
This article demonstrates how to scale an application horizontally by increasing or decreasing the number of pods using kubectl. It also shows how Kubernetes automatically distributes the traffic among the pods using a ClusterIP service.

#### Resource 3: https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/
This article provides a hands-on tutorial on how to enable horizontal pod autoscaling for an example web app. It shows how to create a HorizontalPodAutoscaler resource, how to generate load, and how to monitor the scaling behavior.

#### Resource 4: https://medium.com/@davetech112/kubernetes-scaling-and-load-balancing-ensuring-high-availability-and-performance-17fd0938c986
This article introduces the concept of Ingress, which is an API object that manages external access to the services in a cluster. It also discusses the benefits, challenges, and prerequisites of using Ingress. It also provides some examples of Ingress resources and Ingress controllers.
