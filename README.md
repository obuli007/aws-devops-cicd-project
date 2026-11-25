# AWS DevOps CI/CD Pipeline Automation Using Jenkins, Docker & AWS EC2

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Jenkins](https://img.shields.io/badge/CI%2FCD-Jenkins-red)
![Docker](https://img.shields.io/badge/Container-Docker-blue)
![Python](https://img.shields.io/badge/Language-Python-yellow)
![GitHub](https://img.shields.io/badge/Source%20Control-GitHub-black)
![Status](https://img.shields.io/badge/Project-Completed-success)

---

# 1. Project Overview

This project demonstrates an end-to-end Continuous Integration and Continuous Deployment (CI/CD) pipeline using AWS EC2, Jenkins, Docker, GitHub, Python, and Pytest.

The main objective of this project is to automate the application deployment process and reduce manual intervention.

Whenever developers push code changes to GitHub, Jenkins can receive notifications through a GitHub Webhook and execute the configured CI/CD pipeline.

The pipeline performs the following operations:

1. Fetches application source code from GitHub.
2. Executes automated application tests.
3. Builds a Docker image.
4. Deploys the application inside a Docker container.
5. Performs an application health check.
6. Reports the pipeline execution status.

**Final Result:** A Python web application successfully deployed on AWS EC2 using Docker and Jenkins CI/CD automation.

# 2. Project Objectives

- Understand real-world DevOps workflow.
- Implement Continuous Integration using Jenkins.
- Implement Continuous Deployment using Docker.
- Integrate GitHub with Jenkins.
- Configure GitHub Webhook integration.
- Automate Python application testing.
- Build and manage Docker images and containers.
- Deploy applications on AWS EC2.
- Verify application availability using health checks.
- Understand Linux server administration.

# 3. Architecture Diagram

```text
                 DEVELOPER
                     |
                     |
                Git Push
                     |
                     v
              GITHUB REPOSITORY
                     |
                     |
               GitHub Webhook
                     |
                     v
              JENKINS SERVER
                     |
                     |
              Jenkins Pipeline
                     |
          +----------+----------+
          |          |          |
          v          v          v
       Checkout    Testing   Docker Build
          |          |          |
          +----------+----------+
                     |
                     v
               Docker Image
                     |
                     v
              Docker Container
                     |
                     v
                 AWS EC2
                     |
                     v
             Python Application
                     |
                     v
                Health Check
                     |
                     v
              SUCCESS STATUS
```

## Architecture Explanation

### GitHub

GitHub stores the project source code and provides version control.

### GitHub Webhook

Webhook sends an HTTP notification to Jenkins when a configured repository event occurs.

### Jenkins

Jenkins is responsible for automating the CI/CD workflow through the Jenkinsfile.

### Pytest

Pytest executes automated tests to verify application functionality before deployment.

### Docker

Docker packages the application and its dependencies into a container image.

### AWS EC2

EC2 provides the cloud-based Linux environment where the application runs.

### Health Check

The health check verifies whether the deployed application is responding correctly.

# 4. Technologies Used and Why We Used Them

| Technology | Purpose | Why Used |
|---|---|---|
| AWS EC2 | Cloud Server | To host the application and DevOps environment |
| Amazon Linux | Operating System | To manage the cloud server |
| Git | Version Control | To track source code changes |
| GitHub | Code Repository | To store and manage project code |
| GitHub Webhook | Event Notification | To notify Jenkins about repository changes |
| Jenkins | CI/CD | To automate build, testing and deployment |
| Docker | Containerization | To package and run the application |
| Python | Programming Language | To develop the application |
| Flask | Web Framework | To serve the application and health endpoint |
| Pytest | Testing Framework | To execute automated tests |
| Linux Shell | Command Line | To manage servers and execute commands |
| SSH | Remote Access | To connect securely to EC2 |

# 5. Project Folder Structure

```text
aws-devops-cicd-project/
│
├── app.py
│
├── Dockerfile
│
├── Jenkinsfile
│
├── requirements.txt
│
├── test_app.py
│
├── README.md
│
└── .gitignore
```

## File Explanation

### app.py

Contains the Python application code.

Responsibilities:
- Runs the web application.
- Handles application requests.
- Provides the health check endpoint.

### Dockerfile

Contains instructions to create the Docker image.

Responsibilities:
- Selects the base image.
- Installs application dependencies.
- Copies application files.
- Configures the application port.
- Starts the application.

### Jenkinsfile

Contains the Jenkins Pipeline definition.

Responsibilities:
- GitHub source code checkout.
- Automated testing.
- Docker image building.
- Container deployment.
- Application health verification.

### requirements.txt

Contains Python dependencies required by the application.

Example:

```text
flask
pytest
```

### test_app.py

Contains automated test cases for validating application functionality.

### README.md

Contains complete project documentation.

### .gitignore

Specifies files and folders that should not be tracked by Git.

# 6. AWS EC2 Setup

## What is AWS EC2?

Amazon Elastic Compute Cloud (EC2) is an AWS service that provides virtual servers in the cloud.

We used EC2 to host our DevOps environment and deploy the Python application.

## EC2 Configuration

| Configuration | Value |
|---|---|
| Cloud Provider | AWS |
| Service | EC2 |
| Operating System | Amazon Linux |
| Access Method | SSH |
| Application Port | 8050 |
| Jenkins Port | 8080 |
| Container Platform | Docker |

## Connecting to EC2

From Windows PowerShell:

```powershell
# Navigate to the folder containing your PEM key
cd Downloads

# Connect to EC2 using SSH
ssh -i "your-key.pem" ec2-user@YOUR_EC2_PUBLIC_IP
```

**Explanation:**

- `ssh` – Establishes a secure remote connection.
- `-i` – Specifies the private key file.
- `your-key.pem` – EC2 private key.
- `ec2-user` – Default Amazon Linux login user.
- `YOUR_EC2_PUBLIC_IP` – Public IPv4 address of EC2.

Replace the example key and IP with your actual values.

## Update Linux Packages

```bash
# Refresh available package information
sudo yum update -y
```

Explanation:

- `sudo` – Executes the command with administrator privileges.
- `yum` – Package management tool.
- `update` – Updates installed packages.
- `-y` – Automatically confirms installation prompts.

Note: Amazon Linux 2023 also supports DNF package management.

## Check Linux Information

```bash
# Display operating system information
cat /etc/os-release

# Display current logged-in user
whoami

# Display current directory
pwd

# Display server hostname
hostname

# Display memory information
free -h

# Display disk space
df -h
```

**Why used:** To understand the operating system, user permissions, server resources, and available disk space.

# 7. Git and GitHub Integration

## What is Git?

Git is a distributed version control system used to track changes in source code.

## What is GitHub?

GitHub is a cloud-based platform used to store Git repositories and collaborate on software projects.

## Clone the Repository

```bash
# Download the GitHub repository
git clone https://github.com/obuli007/aws-devops-cicd-project.git

# Navigate into the project directory
cd aws-devops-cicd-project
```

Explanation:

- `git clone` – Downloads the remote repository.
- Repository URL – Identifies the GitHub project.
- `cd` – Changes the current working directory.

## Check Git Status

```bash
# Display current Git working tree status
git status
```

Why used?

To identify modified, untracked, and staged files.

## Add Changes

```bash
# Stage all modified and new files
git add .
```

Why used?

Git add prepares files for the next commit.

## Commit Changes

```bash
# Save changes in local Git history
git commit -m "Update project documentation"
```

Why used?

A commit records a snapshot of the staged changes.

## Push Changes

```bash
# Push local commits to GitHub main branch
git push origin main
```

Explanation:

- `push` – Uploads local commits.
- `origin` – Default remote repository name.
- `main` – Target branch.

## Check Remote Repository

```bash
# Display configured remote repositories
git remote -v
```

Why used?

To verify that the local repository is connected to the correct GitHub repository.

# 8. GitHub Webhook Integration

## What is a Webhook?

A webhook is an HTTP callback that sends an event notification from one application to another.

In this project, GitHub Webhook is configured to notify Jenkins when a repository event occurs.

## Workflow

1. Developer makes changes to application code.
2. Developer pushes changes to GitHub.
3. GitHub sends an event notification to Jenkins.
4. Jenkins receives the notification.
5. Jenkins starts the configured pipeline.

## Why Webhook?

Without webhook integration, Jenkins may need periodic polling to check for code changes.

Webhook-based triggering helps Jenkins respond to repository events without continuous polling.

**Important:** The webhook URL must be configured using the actual reachable Jenkins endpoint. Avoid exposing Jenkins without appropriate authentication and network security.

# 9. Jenkins CI/CD Configuration

## What is Jenkins?

Jenkins is an open-source automation server used to automate software development workflows.

It supports Continuous Integration and Continuous Delivery/Deployment.

## Why Jenkins?

We used Jenkins to automate the following operations:

- Source code checkout.
- Application testing.
- Docker image building.
- Docker container deployment.
- Application health verification.

## Jenkins Pipeline

A Jenkins Pipeline defines the complete build and deployment workflow as code.

Our pipeline is defined in a file named:

```text
Jenkinsfile
```

## Pipeline Stages

### Stage 1: Checkout

Purpose:

To retrieve the latest source code from GitHub.

### Stage 2: Test

Purpose:

To execute Pytest test cases and verify the application before deployment.

### Stage 3: Docker Build

Purpose:

To build a Docker image using the Dockerfile.

### Stage 4: Deploy

Purpose:

To deploy the application inside a Docker container.

### Stage 5: Health Check

Purpose:

To verify that the application responds successfully after deployment.

## Jenkins and Docker Permission

Jenkins needs permission to execute Docker commands.

We configured Docker group access for the Jenkins user.

```bash
# Add Jenkins user to Docker group
sudo usermod -aG docker jenkins

# Restart Jenkins to refresh its service session
sudo systemctl restart jenkins
```

Explanation:

- `usermod` – Modifies an existing Linux user.
- `-aG` – Appends the user to an additional group.
- `docker` – Docker group.
- `jenkins` – Jenkins service account.
- `systemctl restart` – Restarts the Jenkins service.

## Verify Jenkins Docker Access

```bash
# Check whether Jenkins can communicate with Docker
sudo -u jenkins docker version
```

Why used?

To confirm that Jenkins can execute Docker commands without permission errors.

Expected result:

Docker Client and Server version information should be displayed.

Note: Group membership changes may require a service restart or new login session. Use least-privilege access and secure Docker administration.

# 10. Docker Implementation

## What is Docker?

Docker is a containerization platform that packages applications and their dependencies into portable containers.

## Why Docker?

We used Docker to:

- Package the Python application.
- Maintain a consistent application environment.
- Simplify application deployment.
- Manage application containers.
- Run the application independently of the host environment.

## Dockerfile

The Dockerfile defines the instructions required to create the application image.

Example structure:

```dockerfile
# Use an official Python base image
FROM python:3.11-slim

# Set the working directory
WORKDIR /app

# Copy dependency file
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application source code
COPY . .

# Expose application port
EXPOSE 8050

# Start the Python application
CMD ["python", "app.py"]
```

Explanation:

| Instruction | Purpose |
|---|---|
| FROM | Selects the base image |
| WORKDIR | Sets the working directory |
| COPY | Copies files into the image |
| RUN | Executes commands during image building |
| EXPOSE | Documents the application port |
| CMD | Defines the default startup command |

The above is an illustrative Dockerfile structure. Keep the actual project Dockerfile as the source of truth.

## Docker Commands

### Check Docker Version

```bash
# Display Docker version
docker --version
```

Why used?

To verify that Docker is installed.

### Check Docker Service

```bash
# Check Docker service status
sudo systemctl status docker
```

Why used?

To verify that the Docker daemon is running.

### Start Docker Service

```bash
# Start Docker daemon
sudo systemctl start docker
```

### Enable Docker at Boot

```bash
# Automatically start Docker after server restart
sudo systemctl enable docker
```

### Build Docker Image

```bash
# Build image from Dockerfile
docker build -t aws-devops-cicd-project:v1 .
```

Explanation:

- `docker build` – Builds an image.
- `-t` – Assigns an image name and tag.
- `aws-devops-cicd-project` – Image name.
- `v1` – Image version.
- `.` – Uses the current directory as build context.

### List Docker Images

```bash
# Display locally available images
docker images
```

Why used?

To verify that the Docker image was created successfully.

### Run Docker Container

```bash
# Run the application in detached mode
docker run -d \
  --name aws-devops-cicd-container \
  -p 8050:8050 \
  aws-devops-cicd-project:v1
```

Explanation:

- `docker run` – Creates and starts a container.
- `-d` – Runs in detached mode.
- `--name` – Assigns a container name.
- `-p` – Maps host and container ports.
- `8050:8050` – Maps host port 8050 to container port 8050.

### List Running Containers

```bash
# Display currently running containers
docker ps
```

Why used?

To verify whether the application container is running.

### List All Containers

```bash
# Display running and stopped containers
docker ps -a
```

### View Container Logs

```bash
# Display application container logs
docker logs aws-devops-cicd-container
```

Why used?

To troubleshoot application startup errors and inspect application output.

### Stop Container

```bash
# Stop a running container
docker stop aws-devops-cicd-container
```

### Remove Container

```bash
# Remove a stopped container
docker rm aws-devops-cicd-container
```

### Remove Docker Image

```bash
# Remove a Docker image
docker rmi aws-devops-cicd-project:v1
```

Important:

Do not remove an image that is still required by a running container.

# 11. Python Application and Automated Testing

## What is Pytest?

Pytest is a Python testing framework used to execute automated test cases.

## Why Pytest?

We used Pytest to verify application functionality before deploying the application.

## Install Dependencies

```bash
# Install all dependencies listed in requirements.txt
pip install -r requirements.txt
```

Explanation:

- `pip` – Python package installer.
- `install` – Installs required packages.
- `-r` – Reads package names from a requirements file.

## Run Tests

```bash
# Execute all test cases
pytest -v
```

Explanation:

- `pytest` – Starts the testing framework.
- `-v` – Displays detailed test execution information.

Expected result:

```text
============================= test session starts ==============================

collected 2 items

test_app.py ..                                                     [100%]

============================== 2 passed ========================================
```

**Actual project result: 2 tests passed.**

This confirms that both configured test cases completed successfully.

# 12. Application Deployment

## Application Details

| Configuration | Value |
|---|---|
| Application Language | Python |
| Framework | Flask |
| Container Platform | Docker |
| Cloud Platform | AWS EC2 |
| Container Name | aws-devops-cicd-container |
| Docker Image | aws-devops-cicd-project:v1 |
| Application Port | 8050 |

## Verify Application

```bash
# Check application response
curl http://localhost:8050/
```

Why used?

To verify that the application responds to HTTP requests from the EC2 server.

## Verify Application Health

```bash
# Check application health endpoint
curl http://localhost:8050/health
```

Expected response:

```json
{
  "status": "healthy"
}
```

Why used?

To confirm that the deployed application is responding successfully.

## Access Application from Browser

```text
http://YOUR_EC2_PUBLIC_IP:8050/
```

Replace `YOUR_EC2_PUBLIC_IP` with the actual EC2 public IP.

The EC2 security group must allow inbound TCP traffic on port 8050 for the intended access. For production, restrict access and use HTTPS through a suitable reverse proxy or load balancer.

# 13. Complete CI/CD Workflow

The following workflow describes how the configured Jenkins pipeline operates.

**Step 1 – Developer Code Changes**

The developer modifies the application source code.

**Step 2 – GitHub Push**

The changes are committed and pushed to the GitHub main branch.

**Step 3 – Webhook Notification**

GitHub sends a webhook notification to Jenkins.

**Step 4 – Jenkins Checkout**

Jenkins retrieves the latest repository contents.

**Step 5 – Automated Testing**

Jenkins executes the Pytest test cases.

**Step 6 – Docker Image Build**

Jenkins builds the application Docker image.

**Step 7 – Docker Deployment**

Jenkins deploys the application inside a Docker container.

**Step 8 – Health Verification**

Jenkins checks the application health endpoint.

**Step 9 – Pipeline Result**

Jenkins reports the final build status.

# 14. Troubleshooting Commands

## Check Running Docker Containers

```bash
docker ps
```

Use this command when the application is not accessible.

## Check Container Logs

```bash
docker logs aws-devops-cicd-container
```

Use this command to identify application startup or runtime errors.

## Check Docker Service

```bash
sudo systemctl status docker
```

Use this command if Docker commands cannot communicate with the Docker daemon.

## Check Jenkins Service

```bash
sudo systemctl status jenkins
```

Use this command to verify whether Jenkins is running.

## Restart Jenkins

```bash
sudo systemctl restart jenkins
```

Use this command after Jenkins service configuration changes.

## Check Disk Space

```bash
df -h
```

Use this command to identify disk-space problems.

## Check Docker Disk Usage

```bash
docker system df
```

Use this command to understand Docker image, container, and cache storage usage.

## Check Application Port

```bash
sudo ss -tulnp
```

Use this command to identify listening ports and associated processes.

## Check Application Health

```bash
curl -i http://localhost:8050/health
```

Use this command to inspect the HTTP response and status code.

# 15. Security Best Practices

- Never upload AWS access keys or secret keys to GitHub.
- Never upload PEM private keys.
- Use IAM roles and least-privilege permissions where applicable.
- Protect Jenkins with authentication.
- Restrict EC2 security group inbound rules.
- Avoid exposing Jenkins port 8080 publicly without appropriate protection.
- Avoid exposing Docker daemon TCP access.
- Use HTTPS for public application access.
- Keep operating system and application dependencies updated.
- Store sensitive credentials in Jenkins Credentials or an appropriate secrets manager.

# 16. Final Project Execution Results

The following stages were successfully executed during the project implementation.

| Pipeline Stage | Result |
|---|---|
| GitHub Repository Integration | Successful |
| Source Code Checkout | Successful |
| Automated Testing | 2 Tests Passed |
| Docker Image Build | Successful |
| Docker Container Deployment | Successful |
| Application Execution | Successful |
| Application Health Check | Successful |

**Final Project Status: Successfully Implemented**

The Python application was deployed on AWS EC2 using Docker, and the Jenkins pipeline completed its configured stages successfully.

# 17. Skills Gained from This Project

### AWS Cloud

- EC2 instance creation and management.
- Linux server administration.
- Security group configuration.
- SSH-based server access.

### DevOps

- CI/CD pipeline implementation.
- Jenkins Pipeline configuration.
- GitHub Webhook integration.
- Automated application deployment.

### Docker

- Docker image creation.
- Dockerfile configuration.
- Container lifecycle management.
- Application port mapping.
- Container troubleshooting.

### Development and Testing

- Python application execution.
- Flask web application fundamentals.
- Pytest automated testing.
- HTTP health checks.

### Version Control

- Git repository management.
- GitHub integration.
- Branch management.
- Commit and push operations.



#  Project Information

**Project Name:** AWS DevOps CI/CD Pipeline Automation

**Author:** Obuliraj

**GitHub Username:** obuli007

**GitHub Repository:**

https://github.com/obuli007/aws-devops-cicd-project

**Project Type:** Hands-on AWS and DevOps Practical Project

**Project Status:** Completed

---

## Conclusion

This project provided practical experience in implementing an automated CI/CD workflow using AWS EC2, Jenkins, Docker, GitHub, Python, and Pytest.

It demonstrates how application source code can be tested, packaged, deployed, and verified through an automated DevOps pipeline.

The project helped develop practical knowledge of cloud infrastructure, Linux administration, source code management, containerization, CI/CD automation, and application deployment.

**Thank you for visiting my project!**