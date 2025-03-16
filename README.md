# CI/CD Pipeline with Docker and Jenkins

This repository contains the code for setting up a Continuous Integration/Continuous Deployment (CI/CD) pipeline using Docker and Jenkins. The pipeline automates the process of building, testing, and deploying applications, ensuring efficiency and consistency in software development workflows.

## Overview

The CI/CD pipeline involves the following steps:

1. **GitHub Push**: The process begins when code changes are pushed to the GitHub repository.
2. **Jenkins Build Trigger**: Jenkins, our automation server, is configured to monitor the GitHub repository for changes. Upon detecting a new commit, Jenkins triggers the build process.
3. **Docker Image Creation**: Jenkins pulls the base Docker image from DockerHub and builds a Docker image containing the application and its dependencies.
4. **Docker Image Push**: Once the Docker image is built successfully, Jenkins pushes the image to DockerHub, making it available for deployment.
5. **Update Status**: Jenkins updates the build status on GitHub, providing visibility into the CI/CD process.
6. **Notification**: Users are notified of the build status through GitHub notifications.

## Getting Started

Follow the steps below to set up the CI/CD pipeline in your environment:

### 1. **Clone the Repository**
Clone this repository to your local machine using the following command:
   ```bash
   git clone https://github.com/basuru07/GitHub-Docker-and-Jenkins-CI-CD-Pipeline.git
```
### 1. **Pipeline Stage Overview**
<p align="center">
  <img src="https://github.com/user-attachments/assets/8ef58ad4-daf5-439c-a03a-b2b0f9284279" width="500"/>
</p>
