pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checkout completed'
            }
        }

        stage('Test') {
            steps {
                echo 'Starting Python Tests'
                sh '''
                    docker run --rm \
                    -v "$WORKSPACE:/app" \
                    -w /app \
                    python:3.11-slim \
                    sh -c "pip install -r requirements.txt && pytest -v"
                '''
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker Image'
                sh '''
    docker build -t aws-devops-cicd-project:v${BUILD_NUMBER} .
    docker tag aws-devops-cicd-project:v${BUILD_NUMBER} aws-devops-cicd-project:latest
'''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application'
                sh '''
                    docker rm -f aws-devops-cicd-container || true
                    docker run -d \
                    --name aws-devops-cicd-container \
                    -p 8050:8050 \
                    aws-devops-cicd-project:v1
                '''
            }
        }

        stage('Health Check') {
            steps {
                echo 'Checking Application Health'
                sh '''
                    sleep 5
                    curl -f http://localhost:8050/health
                '''
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline Completed Successfully!'
        }
        failure {
            echo 'CI/CD Pipeline Failed!'
        }
    }
}

