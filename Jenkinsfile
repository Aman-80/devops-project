pipeline {
    agent any

    stages {



        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop devops-container || true'
                sh 'docker rm devops-container || true'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 3001:3000 --name devops-container devops-app'
            }
        }
    }
}