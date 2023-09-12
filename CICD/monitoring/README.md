# Script
In this lesson, you will learn how we can setup proper monitoring channels and alerts for our CICD pipeline. So, let's get started.

Implementing monitoring and alerting in a Continuous Integration/Continuous Deployment (CICD) pipeline is essential for ensuring the stability, reliability, and performance of your software applications. Monitoring allows us to collect and analyze data from various stages of our pipeline and our application's runtime environment.

You can learn more about the importance of monitoring the feedback loops in CICD, using the following links:

#### Resourece 1: https://resources.github.com/devops/tools/monitoring/
This article explains, how you can automate your DevOps monitoring process.

#### Resource 2: https://www.techtarget.com/searchitoperations/tip/How-to-achieve-continuous-feedback-in-DevOps-pipelines

#### Resource 3: https://www.browserstack.com/guide/devops-feedback-loop

Now, let me show you, how we've configured our monitoring tools in our CICD pipeline. Here I'm using Grafana and Prometheus to monitor our CICD pipeline, which we've configured using Github Actions.

For your information, [Prometheus](https://prometheus.io/) is an open-source monitoring and alerting toolkit that can scrape and store time-series data.

And [Grafana](https://grafana.com/) is a popular open-source platform for creating dashboards and visualizing metrics.


