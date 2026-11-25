Automatic CI/CD Webhook Testing# AWS DevOps CI/CD Project

## Project Overview
An end-to-end CI/CD automation project
using AWS, Jenkins, Docker and Terraform.

## Technologies
- AWS EC2
- Jenkins
- Docker
- Terraform
- Git and GitHub
- Python Flask
- Linux

## Application Features
- Home endpoint
- Health check endpoint
- Automated unit testing

## Project Goal
To automate application build, testing,
containerization and deployment on AWS.



# End-to-End AWS DevOps CI/CD Automation Project

## 1. Project Overview

This project demonstrates an end-to-end DevOps workflow by developing, testing, containerizing, and deploying a Python Flask application using AWS and DevOps tools.

The main objective is to automate application build, testing, and deployment using a Jenkins CI/CD pipeline.

## 2. Technologies Used

| Technology | Purpose |
|---|---|
| Python Flask | Web application development |
| Git | Version control |
| GitHub | Source code repository |
| Jenkins | CI/CD automation |
| Docker | Application containerization |
| Docker Hub | Docker image registry |
| AWS EC2 | Cloud application hosting |
| Terraform | Infrastructure as Code |
| Linux | Server administration |

## 3. Project Architecture

Developer → GitHub → Jenkins → Automated Testing → Docker Build → Docker Hub → AWS EC2 → Live Application

## 4. Project Directory Structure

```text
aws-devops-cicd-project/
│
├── app.py
├── requirements.txt
├── test_app.py
├── README.md
└── .gitignore
```

## 5. Application Development

### app.py

Created a Python Flask application with two endpoints:

- `/` - Displays application information.
- `/health` - Checks application health status.

The application runs on port 8050 and listens on all network interfaces using `0.0.0.0`.

### requirements.txt

Contains the Python dependencies required for the application.

- Flask - Web application framework.
- pytest - Python testing framework.

### test_app.py

Created automated test cases to verify:

- Home endpoint returns HTTP 200.
- Health endpoint returns HTTP 200.

### .gitignore

Prevents unnecessary files from being tracked by Git.

Excluded files and directories:

- venv/
- __pycache__/
- .pytest_cache/
- .env
- *.pyc

## 6. Commands Used – Windows PowerShell

### Step 1: Navigate to project directory

```powershell
cd C:\Users\Dell\Downloads
```

**Explanation:** Changes the current working directory.

```powershell
mkdir aws-devops-cicd-project
```

**Explanation:** Creates a new project folder.

```powershell
cd aws-devops-cicd-project
```

**Explanation:** Navigates into the project folder.

```powershell
code .
```

**Explanation:** Opens the current folder in Visual Studio Code.

### Step 2: Check Python installation

```powershell
python --version
```

**Explanation:** Displays the installed Python version.

### Step 3: Create virtual environment

```powershell
python -m venv venv
```

**Explanation:** Creates an isolated Python environment for project dependencies.

### Step 4: Activate virtual environment

```powershell
.\venv\Scripts\Activate.ps1
```

**Explanation:** Activates the virtual environment in Windows PowerShell.

### Step 5: Install dependencies

```powershell
pip install -r requirements.txt
```

**Explanation:** Installs all Python packages listed in requirements.txt.

### Step 6: Run automated tests

```powershell
pytest -v
```

**Explanation:** Executes automated test cases with detailed output.

Expected result: 2 tests passed.

### Step 7: Run the application

```powershell
python app.py
```

**Explanation:** Starts the Flask development server.

Application URLs:

- http://127.0.0.1:8050
- http://127.0.0.1:8050/health

## 7. Git and GitHub Commands

### Initialize Git repository

```bash
git init
```

**Explanation:** Initializes a new Git repository.

### Check repository status

```bash
git status
```

**Explanation:** Displays modified, untracked, and staged files.

### Add project files

```bash
git add .
```

**Explanation:** Stages all non-ignored project changes.

### Commit changes

```bash
git commit -m "Initial Python Flask application"
```

**Explanation:** Saves staged changes with a descriptive commit message.

### Rename branch

```bash
git branch -M main
```

**Explanation:** Creates or renames the current branch to main.

### Connect GitHub repository

```bash
git remote add origin https://github.com/YOUR_USERNAME/aws-devops-cicd-project.git
```

**Explanation:** Adds the GitHub repository as the remote named origin.

### Push code to GitHub

```bash
git push -u origin main
```

**Explanation:** Uploads the local main branch to GitHub and establishes upstream tracking.

## 8. Application Testing

Tested the application locally using the following URLs:

| Endpoint | Expected Result |
|---|---|
| `/` | HTTP 200 |
| `/health` | HTTP 200 |

Automated testing is performed using pytest.

## 9. DevOps Workflow

The planned automated workflow includes:

1. Developer pushes code to GitHub.
2. Jenkins retrieves source code.
3. Jenkins executes automated tests.
4. Docker builds the application image.
5. Docker image is pushed to Docker Hub.
6. AWS EC2 pulls and runs the Docker image.
7. Application availability is verified.

## 10. Learning Outcomes

- Python Flask application development.
- Git and GitHub version control.
- Python virtual environment management.
- Dependency installation using pip.
- Automated testing using pytest.
- Project documentation and repository management.
- Understanding end-to-end CI/CD automation.

## 11. Project Status

Phase 1: Application development and GitHub source control.

Further phases: AWS infrastructure provisioning, Docker containerization, Jenkins pipeline automation, and application deployment.

**Note:** This README documents the project implementation progressively. Future tools and deployment steps will be marked completed only after successful practical execution.
