pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t docker-web-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker rm -f webapp || true
                docker run -d -p 9090:80 --name webapp docker-web-app
                '''
            }
        }
    }
}