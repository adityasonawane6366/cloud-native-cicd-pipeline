pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/adityasonawane6366/cloud-native-cicd-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-app:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f cicd-app || true'
                sh 'docker run -d -p 80:5000 --name cicd-app cicd-app:latest'
            }
        }
    }
}
