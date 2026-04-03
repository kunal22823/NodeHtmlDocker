pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/kunal22823/NodeHtmlDocker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-node-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
                sh 'docker run -d -p 8070:3000 --name my-container my-node-app'
            }
        }
    }
}
