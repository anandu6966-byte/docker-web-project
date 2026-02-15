pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t docker-web-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat '''
                docker rm -f webapp
                docker run -d -p 9090:80 --name webapp docker-web-app
                '''
            }
        }
    }
}