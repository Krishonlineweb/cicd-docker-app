pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Krishonlineweb/cicd-docker-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-docker-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
                sh 'docker run -d --name my-container -p 3000:3000 my-docker-app'
            }
        }
    }
}
