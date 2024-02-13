# Text
In this lesson, you will learn about the steps involved in integrating containers into CI/CD pipeline for continuous deployment. So, let's get started.

Integrating containers into a CI/CD (Continuous Integration/Continuous Deployment) pipeline is a common practice to automate the build, test, and deployment processes of software applications. Here are the general steps to integrate containers into your CI/CD pipeline:

1. **Version Control System (VCS):**
Ensure your code is stored in a version control system such as Git. This is a fundamental step for CI/CD as it allows you to track changes and trigger automated processes based on code updates.

2. **Containerization:**
Choose a containerization tool, such as **Docker**. Create a `Dockerfile` to define your application's dependencies, environment, and how it should be packaged into a container.

3. **Setup Container Registry:**
Set up a container registry (for example: Docker Hub, AWS ECR, Google Container Registry) to store and manage your Docker images. Push your Docker images to the registry after building them.

4. **CI/CD Platform:**
Choose a CI/CD platform that supports containerized applications (for example: Jenkins, GitLab CI, Travis CI, GitHub Actions). Configure your CI/CD tool to connect to your VCS.

5. **Pipeline Configuration:**
Create a CI/CD pipeline configuration file (e.g., .gitlab-ci.yml, Jenkinsfile) to define the steps for building, testing, and deploying your application. Include steps to build and push the Docker image to the container registry.

Now, if you want to learn more about how we can implement that, you can follow these resources:

#### Resource 1: https://docs.docker.com/build/ci/
This article provides a self-paced, hands-on tutorial on how to build and share a containerized app using Docker. You will learn how to build images, run containers, use volumes, and define your application using Docker Compose. You will also learn about some advanced topics, such as networking and image building best practices.

#### Resource 2: https://cloud.google.com/kubernetes-engine/docs/tutorials/gitops-cloud-build
This article shows you how to create a CI/CD pipeline that automatically builds a container image from committed code, stores the image in Artifact Registry, updates a Kubernetes manifest in a Git repository, and deploys the application to Google Kubernetes Engine using that manifest.

#### Resource 3: https://www.infoq.com/articles/continuous-deployment-containers/
This article provides a solution idea for creating a CI/CD pipeline for your containerized apps on Azure DevOps. You will learn how to build a Docker image, push it to the Azure Container Registry, update a Kubernetes manifest, and deploy the application to Azure Kubernetes Service.
