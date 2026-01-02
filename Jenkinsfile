pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/YOUR_USER/cicd-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker rm -f myapp || true'
                sh 'docker run -d -p 80:5000 --name myapp myapp:latest'
            }
        }
    }
}
