# Advanced AWS CI/CD Pipeline using Jenkins

## Overview
This repository contains a Jenkins pipeline that supports multiple projects and environments.

## Architecture Diagram

![Pipeline Flow](https://example.com/aws-ci-diagram.png)

## Features
- Supports multiple projects (projectA, projectB, projectC)
- Deploys to different environments (dev, staging, prod)
- Runs security scanning using Trivy
- Automates Docker builds and AWS ECS deployments

## Prerequisites
- Jenkins installed and configured
- AWS CLI installed and configured
- Docker installed
- Maven installed
- Trivy for security scanning
- AWS ECR and ECS setup

## Setup Instructions
1. **Clone the repository:**
   ```sh
   git clone https://github.com/your-org/ci-pipeline.git
   ```
2. **Set up credentials in Jenkins:**
   - Add AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY as Jenkins credentials.
3. **Configure AWS ECR:**
   ```sh
   aws ecr create-repository --repository-name projectA
   aws ecr create-repository --repository-name projectB
   aws ecr create-repository --repository-name projectC
   ```
4. **Run the pipeline in Jenkins:**
   - Select the project and environment when triggering the build.

## Pipeline Stages
1. **Project Selection**: Determines which project to build.
2. **Checkout Code**: Clones the selected project repository.
3. **Build**: Compiles the application using Maven.
4. **Unit Tests**: Runs automated tests.
5. **Security Scan**: Scans for vulnerabilities using Trivy.
6. **Docker Build and Push**: Builds and pushes the image to AWS ECR.
7. **Deploy to AWS ECS**: Deploys the application to AWS ECS.

## Notes
- Ensure IAM roles are properly configured for Jenkins.
- Modify cluster/service names as per your AWS setup.
