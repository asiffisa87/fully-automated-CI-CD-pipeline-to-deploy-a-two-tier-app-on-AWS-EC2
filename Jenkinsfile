pipeline {
    agent any
    stages {
        stage('Clone Code') {
            steps {
                // Replace with your GitHub repository URL
                git branch: 'main', url: '[https://github.com/asiffisa87/fully-automated-CI-CD-pipeline-to-deploy-a-two-tier-app-on-AWS-EC2.git](https://github.com/your-username/your-repo.git)'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:latest .'
            }
        }
        stage('Deploy with Docker Compose') {
            steps {
                // Stop existing containers if they are running
                sh 'docker compose down || true'
                // Start the application, rebuilding the flask image
                sh 'docker compose up -d --build'
            }
        }
    }
}
