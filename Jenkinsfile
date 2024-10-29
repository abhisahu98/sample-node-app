pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/abhisahu98/sample-node-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("sample-node-app:${env.BUILD_NUMBER}")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 3000:3000 sample-node-app:${env.BUILD_NUMBER}'
                }
            }
        }
    }
}
