pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                docker build -t devops-docker-app:latest -f app/Dockerfile app
                '''
            }
        }

        stage('Verify Docker Image') {
            steps {
                sh 'docker images | grep devops-docker-app'
            }
        }
    }
}
