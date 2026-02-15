pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/USERNAME/docker-web-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-web-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker rm -f my-web-container || true
                docker run -d --name my-web-container -p 9090:80 my-web-app
                '''
            }
        }
    }
}