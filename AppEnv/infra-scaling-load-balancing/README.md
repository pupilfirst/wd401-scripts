# Script
In this lesson, you will learn more load balancing and how we can used to scale applications to distribute traffic efficiently. So, let's get started.

Load balancing is the practice of distributing computational workloads between two or more computers. 

On the Internet, load balancing is often employed to divide network traffic among several servers. This reduces the strain on each server and makes the servers more efficient, speeding up performance and reducing latency. 

You can learn more about Load Balancing, using the following links:

#### Resource 1: https://www.mobindustry.net/blog/how-to-build-scalable-web-applications-challenges-and-solutions/
This article explains what scalability is and how to prepare your software for success and expansion. It covers the main principles of creating scalable web applications, the types of scaling (horizontal vs vertical), the challenges faced in scaling microservices, and the best practices for building scalable web apps.

#### Resource 2: https://www.cloudflare.com/learning/performance/what-is-load-balancing/
This article provides an overview of load balancing, how it works, and why it is essential for most Internet applications. It also explains the differences between static and dynamic load balancing algorithms, as well as the types of load balancers (hardware vs software) and their features.

#### Resource 3: https://www.howtogeek.com/devops/what-are-load-balancers-how-to-effectively-distribute-incoming-traffic/
This article dives deeper into the concept of load balancing and how it improves capacity and redundancy. It describes the role of load balancers, how they select servers to handle requests, and what kinds of algorithms they use. It also compares layer 4 and layer 7 load balancers and their advantages and disadvantages.

Now, let me show you, how we've implemented load balancing in one of our Node.Js application. The server uses two PM2 instances to distribute load in a round robin pattern.
> Action: Show the server log for both instances, then make API calls from Postnan and show two server are receiving the request alternatively.

So, as you can see, our load balancer is working perfectly!

So, that's it for this lesson, see you in the next one.

