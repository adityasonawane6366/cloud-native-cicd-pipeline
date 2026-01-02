pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/adityasonawane6366/cloud-native-cicd-pipeline.git'
            }
        }

        stage('Deploy on EC2') {
            steps {
                sh '''
                docker build -t cicd-app .
                docker rm -f cicd-app || true
                docker run -d -p 80:5000 --name cicd-app cicd-app
                '''
            }
        }
    }
}
