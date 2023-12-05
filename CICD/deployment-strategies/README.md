# Script
In this lesson, you will learn more about different deployment strategies, which are nothing but the methodologies for releasing and updating software applications. These strategies help ensure the stability and reliability of applications during deployment.

### Types of Deployment Strategies

1. **Blue-Green Deployment:** Here we have to maintain two identical environments: one (blue) is currently serving production traffic, and the other (green) is a clone where you deploy the new version. It's suitable for applications that require high availability and minimal downtime.
2. **Canary Deployment:** Here we release new features or changes to a small subset of users or servers before rolling out to the entire user base. It's useful when you want to minimize risks associated with new releases.
3. **Rolling Deployment:** It gradually update instances or nodes one by one while keeping the application available.

Now there are few more deployment strategies available like: Shadow Deployment, A/B testing etc. You can learn more about them from the following resources:

#### Resource 1: https://thenewstack.io/deployment-strategies/
This article gives a comprehensive overview of six common deployment strategies: recreate, ramped, blue-green, canary, A/B testing, and shadow. It also provides some examples of tools and frameworks that can help you implement these strategies, such as Kubernetes, Jenkins, and LambdaTest. 

#### Resource 2: https://www.abtasty.com/blog/deployment-strategies/
This article introduces the concept and definition of deployment strategies and why they are important for software development and delivery. It also discusses four types of deployment strategies: rolling updates, blue-green deployments, canary releases, and feature flags. 

### Resource 3: https://www.youtube.com/watch?v=lj5T9lO5KBs
This video demonstrates how to use GitHub Actions to automate Canary deployments. Here you'll be able to learn, how to deploy a simple service using the Microsoft Azure Container Apps service, and then using GitHub actions how we can automatically deploy and test new versions  when some changes are made in the application code.

So, that's it for this lesson, see you in the next one.