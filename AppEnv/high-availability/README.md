# Text
In this lesson, you will learn about High Availability (HA) and Disaster Recovery (DR). High availability, simply put, is eliminating single points of failure and disaster recovery is the process of getting a system back to an operational state when a system is rendered inoperative. So, let's get started.

## High Availability
High availability is keeping your systems running and minimizing downtime so that customers can use your services uninterruptedly. Achieving high availability involves designing redundancy and fault tolerance into your IT infrastructure. There are basically 3 kinds of redundancy that are implemented in most systems: hardware, software, and environmental.

Here are some strategies for ensuring high availability, encompassing hardware, software, and network redundancy:
### 1. Redundant Hardware:
- Deploy redundant servers, storage arrays, and networking equipment within a data center. This ensures that if one piece of hardware fails, another takes over seamlessly.
- Use RAID (Redundant Array of Independent Disks) configurations to protect against hard drive failures and data loss.

### 2. Redundant Software:
- Implement failover clustering at the software level. This involves running multiple instances of a software service across different servers, so if one instance fails, another can take over.
- Use virtualization or containerization to create redundant software environments that can be quickly switched if an issue arises.

### 3. Network Redundancy:
- Establish redundant network paths with diverse routes to minimize the risk of network failures.
- Use multiple internet service providers (ISPs) and BGP (Border Gateway Protocol) routing for internet connectivity redundancy.

## Disaster Recovery
Disaster recovery picks up where high availability fails. Disaster recovery can be as simple as restoring from a backup. A well-defined disaster recovery plan minimizes the downtime. Here's how redundancy plays a role in disaster recovery:

### 1. Redundant Data Centers:
- Maintain redundant data centers in geographically diverse locations to protect against regional disasters.
- Implement data replication between data centers for continuous data availability.

### 2. Geographical Redundancy:
- Use cloud-based services to provide redundancy for critical applications and data.

### 3. Redundant Data Backups:
- Regularly back up critical data and ensure backups are stored offsite or in a geographically distant location.
- Employ multiple backup solutions to guarantee data recoverability.

You can learn more about Load Balancing, using the following links:
#### Resource 1: https://www.atmosera.com/blog/high-availability-vs-disaster-recovery/
This article explores the difference between fault tolerance and disaster recovery, two approaches for ensuring system availability and resilience.

#### Resource 2: https://blog.probax.io/high-availability-vs-disaster-recovery
This article provides an infographic that summarizes the key findings of a survey on the state of resilience in 2023. It covers topics such as the types of data protection technologies used, the causes and impacts of failures, and the recovery time and point objectives.

So, that's it for this lesson, see you in the next one.
