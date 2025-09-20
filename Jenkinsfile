pipeline {
    agent any
    environment {
        IMAGE_BACKEND = "task-manager-backend"
        IMAGE_FRONTEND = "task-manager-frontend"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/navaneethan0312/task-manager.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    sh 'docker-compose build'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'docker-compose up -d'
                }
            }
        }
        stage('Verify') {
            steps {
                echo "Application deployed. Visit http://localhost:3000"
            }
        }
    }
}
